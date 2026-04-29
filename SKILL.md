---
name: pdf-translator
description: Translate English PDF books into natural Chinese with three quality modes. Preserves original meaning sentence-by-sentence while producing fluent Chinese prose. Use this skill whenever the user wants to translate a PDF book, convert English books to Chinese, localize English content into Chinese, or mentions "翻译", "汉化", "英译中", "PDF翻译", "精翻", "速译" in the context of PDF or document translation. Also triggers for "translate this book", "帮我翻译这本", "汉化这个PDF", or any task where English PDF content needs to become natural Chinese text.
---

# PDF Book Translator (English → Chinese)

Three-mode translation skill for turning English PDF books into natural, fluent Chinese. The core commitment is **sentence-by-sentence fidelity** — every sentence in the original must exist in the translation, with no meaning added or lost — while reading as if written by a skilled Chinese author.

## Modes

Choose the right depth for the task:

| Mode | Trigger | Steps | Best for |
|------|---------|-------|----------|
| **Quick** 速译 | "快翻", "quick", "速译" | Read → Translate | Quick look, short standalone pieces, checking what a passage says |
| **Normal** 标准 | default, "翻译", "汉化" | Analyze → Translate | Most book chapters, blog posts, general content |
| **Refined** 精翻 | "精翻", "refined", "精细翻译" | Analyze → Draft → Review → Revise → Polish | Publication-quality output, key chapters, final delivery |

### Auto-detection
- "快翻", "quick", "直接翻译", "快速翻译", "速译" → **Quick**
- "精翻", "refined", "精细翻译", "出版级", "深度翻译", "精译" → **Refined**
- Everything else → **Normal** (default)

### Mode upgrade
After Normal mode completes, ask:
> 翻译已保存。如需进一步审校润色，回复 **"继续润色"** 或 **"refine"**。

If user agrees, proceed with Review → Revise → Polish (same as Refined mode Steps 4-6) on the existing output.

## Style Presets

Control the voice and tone of the Chinese output:

| Style | When to use | Characteristics |
|-------|-------------|-----------------|
| `literal` 逐句忠实 | Technical manuals, legal docs, when precision is paramount | Closest to English sentence structure, minimal restructuring |
| `storytelling` 叙事流畅 | Novels, memoirs, narrative non-fiction | Smooth transitions, vivid phrasing, natural Chinese rhythm |
| `elegant` 文采典雅 | Literary fiction, poetry, refined essays | Polished prose, four-character phrases, rhythmic beauty |
| `academic` 学术严谨 | Scholarly works, textbooks, research | Formal register, precise terminology, citation-aware |
| `conversational` 口语自然 | Dialogue-heavy books, informal memoirs, self-help | Casual, approachable, as if speaking to the reader |

If no style is specified, detect from the book's content and tone. For most books, `storytelling` is a safe default. `literal` is recommended for technical reference material.

## Core Translation Philosophy

### 信 Faithfulness — The anchor
- Every English sentence must have a corresponding Chinese sentence
- Facts, numbers, logic, and proper names must match exactly
- Never summarize, skip, or embellish
- Every paragraph break, emphasis, and structural choice from the original must be preserved

### 达 Fluency — The craft  
- The Chinese must read naturally, **not like translated text**
- Reorder clauses into natural Chinese topic-comment structure
- Drop unnecessary English connectives (and, but, that, which)
- Break long English sentences into natural Chinese breath groups (意群), 7-15 characters each
- Use proper Chinese rhythm: alternate long and short sentences
- **Active voice over passive**: Chinese uses 被 far less than English uses passive. Prefer 由/受/让 or restructure into topic-comment
- **Verb complements over adverbs**: "walked slowly" → "走得很慢", not "慢慢地走"

### 雅 Cultural Adaptation — The art
- When English idioms, slang, cultural references, or metaphors cannot be directly translated, find Chinese equivalents that convey the same meaning and emotional impact
- Think about what a Chinese reader would understand, not what the English words literally say
- For cultural references unknown to Chinese readers, add brief inline explanation: **（译注：...）**
- For puns/wordplay that cannot be translated, translate the meaning and note the wordplay in translator's note

## Native Chinese Quality Checklist

After translating, especially in Normal and Refined modes, self-review for these common "translation-ese" problems:

### Europeanized Chinese (欧化中文) — The 6 Red Flags

1. **过度使用"被"字句**: "He was praised" → "他受到了表扬" (not "他被表扬了")
2. **不必要的连接词堆砌**: "因为...所以...", "虽然...但是...", "当...的时候" — Chinese often omits these when context is clear
3. **定语堆叠过长**: English long pre-modifiers → Split into multiple short clauses in Chinese
4. **"之一"泛滥**: "one of the most..." → "极其..." / "...得很", not always "...之一"
5. **"的"字密度过高**: If three or more 的 appear in one sentence, restructure
6. **名词化泛滥**: "the implementation of..." → "实施..." (verb), not "...的实施" (noun phrase)

### Rhythm & Breath

- Read the Chinese aloud in your mind. Does it breathe naturally?
- Alternate sentence lengths. Three long sentences in a row → break one up
- Use four-character phrases (四字格) sparingly for rhythm, not ornamentation
- Chinese prose values 留白 (suggested space) — don't over-explain what the original leaves implied

## Output Format

Chinese-only translation. Do NOT include the English original. The reader wants a clean Chinese reading experience.

### Full book structure

```
# [Book Title] — 中文翻译

## 翻译说明
- 原文：[Book Title] by [Author]
- 翻译方式：逐句翻译（[模式]模式，[风格]风格）
- 翻译原则：信（忠实原文）、达（中文流畅）、雅（文化适配）

---

## Chapter N: [Chapter Title]

### [Section heading if any]

中文翻译段落内容。

中文翻译段落内容。

---

*— 第 N 章完 —*
```

- Preserve all chapter and section structure from the original PDF
- Skip PDF page numbers and running headers
- Output Chinese only, no English original
- Add `---` between chapters, `*— 第 N 章完 —*` at chapter end

## Workflow

### Step 0: Choose Mode & Style

If the user hasn't specified, auto-detect from their phrasing. For books, Normal mode is the default starting point. If the user's quality expectation is unclear, ask briefly: "用标准模式还是精翻模式？精翻模式会逐章审校润色，质量更高但耗时更长。"

### Step 1: Pre-Translation Analysis

**Quick mode**: Skip analysis, translate directly.

**Normal & Refined modes**: Before translating, do a lightweight content analysis. Save as `[book-title]-analysis.md`:

```
## 内容概要
- 主题领域、核心论点
- 作者背景和写作立场
- 目标读者

## 术语提取
| 英文 | 中文 | 备注 |
|------|------|------|
| term | 翻译 | context |

## 语气与风格
- 正式/口语化？幽默/严肃？
- 叙事视角（第一人称/第三人称/全知？）
- 建议的翻译风格：[style preset]

## 翻译难点预警
- [具体段落/表达] → 难点类型（隐喻/文化梗/长难句/双关）→ 建议处理方式
```

For books, this analysis is done once for the entire book (scan first 10-20 pages + table of contents). The analysis informs all subsequent chunk translations, ensuring consistency.

### Step 2: Read & Translate

**Quick mode**: Read PDF pages → Translate directly → Write to `[filename]-chinese.md`.

**Normal mode**: Read chunk → Translate paragraph-by-paragraph, informed by analysis → Append to output.

**Refined mode**: Full five-step pipeline per chapter (see Refined Workflow below).

### Step 3: Chunking Strategy for Books

Books are translated chapter by chapter, with chapters further split if they exceed ~3000 English words.

For each chunk:
1. Read the PDF pages using the Read tool
2. Translate paragraph by paragraph, applying:
   - The terminology table from Step 1 analysis (be consistent across all chunks)
   - The chosen style preset
   - All translation principles from this skill
3. Self-check: Did every English sentence get translated? Does the Chinese read naturally?
4. Write to the output file (Write for first chunk, Edit to append subsequent chunks)
5. Report progress: "已翻译 第N章 (Px-Py)，共约 Z 页"

**Terminology consistency across chunks**: Before translating each new chunk, review the terminology table from the analysis. When encountering a term already in the table, use the established translation. When encountering a new term, add it to the table.

### Resuming interrupted work
1. Read the existing output file and analysis file to find where translation stopped
2. Check which pages/chapters remain
3. Continue from the next un-translated page

## Refined Mode: Full Five-Step Pipeline

For publication-quality output. Each step reads the previous step's output and builds on it. All intermediate files are saved.

### Step R1: Analyze (same as Step 1 above)
Save to `[book-title]-analysis.md`

### Step R2: Draft
Translate the full chapter, applying analysis findings. Save to `[chapter]-draft.md`. This is the raw translation — it will be refined.

### Step R3: Critical Review
Review the draft against the original. **Diagnosis only — no rewriting yet.** Save to `[chapter]-critique.md`:

```
## 准确性
- [问题]: [位置] — [描述：增译/漏译/误译/术语不一致]

## 中文自然度（欧化中文检查）
- [问题]: [原译] → [建议改法]

## 文化适配
- [术语/隐喻]: [当前译法] → [建议调整及理由]

## 总结
[共发现 X 处准确性问题，Y 处表达问题]
```

Key review lens — flag any sentence that reads as "translated" rather than "written":
- Unnatural word order that mirrors English
- Stiff phrasing that a native Chinese writer would never produce
- Overuse of 被/的/之一/当...时/如果...那么
- Metaphors translated literally that sound foreign in Chinese
- Emotional tone flattened or shifted

### Step R4: Revise
Apply all findings from the critique. Save to `[chapter]-revision.md`. Fix all accuracy issues, rewrite unnatural expressions, adjust notes, improve flow.

### Step R5: Polish
Final pass for publication quality:
- Read the entire translation as a standalone piece — does it flow as native content?
- Smooth remaining rough transitions
- Ensure consistent narrative voice and style throughout
- Final terminology consistency check
- Save final to `[chapter]-chinese.md`

## Handling Special Content

### Images & diagrams in PDF
- Note them in place: `[图片：描述]`
- After translation, if the PDF contains text-heavy images (diagrams, charts, screenshots), remind the user: "文中插图可能仍含英文原文，需要手动本地化。"
- Do not attempt to translate image text unless the user specifically asks

### Footnotes & endnotes
- Translate footnote text but keep footnote numbers
- Preserve footnote placement (page bottom or chapter end)

### Code, formulas, technical notation
- Keep exactly as-is — no translation

### Tables
- Translate cell by cell
- Preserve table structure exactly

### Dialogue
- Use 「」 quotation marks for dialogue in Chinese (consistent throughout)
- Add speech rhythm particles: 啊, 吧, 呢, 嘛 where natural
- Preserve character voice: a professor and a teenager must sound different in Chinese

## Configuration (EXTEND.md)

Optional. Create `.pdf-translator/EXTEND.md` in the project root to set persistent preferences:

```yaml
target_language: zh-CN
default_mode: normal        # quick | normal | refined
style: storytelling         # literal | storytelling | elegant | academic | conversational
audience: general           # general | technical | academic | young-readers
chunk_max_words: 3000

glossary:
  "term": "翻译"
  "another term": "另一个翻译"

glossary_files:
  - custom-glossary.md
```

If EXTEND.md is not found, ask once and save. If found, use it. If the user wants to change mid-session, they can just say so.

## Example

### Input (English PDF paragraph):

> The old man had taught the boy to fish and the boy loved him. He was an old man who fished alone in a skiff in the Gulf Stream and he had gone eighty-four days now without taking a fish. In the first forty days a boy had been with him. But after forty days without a fish the boy's parents had told him that the old man was now definitely and finally salao, which is the worst form of unlucky.

### Output (storytelling style):

老头儿教过那孩子打鱼，孩子也爱他。他是个独自在湾流里的一只小船上打鱼的老头儿，他如今已经接连八十四天一条鱼也没打着了。头四十天里，有个孩子跟他在一起。可是过了四十天一条鱼都没打到，孩子爹妈就跟他说，这老头儿如今是彻底"倒了血霉"（salao），意思就是倒霉到了极点。

## Reference Files

- `references/translation-guide.md` — Detailed EN→ZH sentence transformation patterns, domain-specific glossaries, dialogue handling. Read when dealing with complex passages.
- `references/glossary-en-zh.md` — Built-in English→Chinese terminology glossary for common terms with non-obvious translations. Consult when translating technical or specialized content.
- `references/refined-workflow.md` — Extended guidelines for the Refined mode five-step pipeline. Read when user selects Refined mode.

## Quick Reference: Pre-Flight Checklist

Before delivering any translation, verify:
- [ ] Every English sentence has a corresponding Chinese sentence
- [ ] Numbers, dates, proper names match the original exactly
- [ ] No sentence reads as obvious "translation-ese" (被/的/之一 abuse)
- [ ] Paragraph structure matches the original
- [ ] Terminology is consistent (check against analysis/glossary)
- [ ] Chapter/section headings are translated and formatted correctly
