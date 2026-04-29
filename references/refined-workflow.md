# Refined Mode — Full Workflow Guide

Detailed guidelines for the Refined mode five-step pipeline. Read this entire file when the user selects Refined mode (精翻) or upgrades from Normal mode.

## Overview

```
Step R1: Analyze → Step R2: Draft → Step R3: Review → Step R4: Revise → Step R5: Polish
```

Each step reads the previous output and builds on it. All intermediate files are saved so the user can inspect the translation process. Steps R3-R5 are handled by the main agent, not subagents.

---

## Step R1: Content Analysis

Before translating, understand the material deeply. Save to `[book-title]-analysis.md`.

### 1.1 Content Summary
- What is this book/chapter about? What is the core argument or narrative?
- Who is the author? What is their background, stance, and writing context?
- Who is the intended audience of the original?
- What is the purpose — to inform, persuade, entertain, teach?

### 1.2 Terminology Extraction
Scan the content and extract:
- Technical terms and jargon
- Proper nouns, brand names, acronyms
- Repeated key concepts
- Domain-specific expressions

Cross-reference with `references/glossary-en-zh.md`. For terms not in glossary, determine standard Chinese translations. Record in a table:

```
| English | Chinese | Notes |
|---------|---------|-------|
| term | 翻译 | context/domain |
```

### 1.3 Tone & Style Assessment
- **Register**: Formal, conversational, academic, colloquial?
- **Voice**: First person, third person, omniscient narrator?
- **Features**: Humor? Metaphor density? Cultural references? Wordplay?
- **Suggested style preset**: Based on assessment, choose from: literal / storytelling / elegant / academic / conversational
- **Sentence rhythm**: Short and punchy? Long and flowing? Mixed?

### 1.4 Translation Challenges Map
Identify what will cause difficulty:

| Type | Examples | Approach |
|------|----------|----------|
| **Comprehension gaps** | Terms/references target readers won't know | Add brief inline explanation  |
| **Figurative language** | Metaphors, idioms, expressions | Interpret meaning → find Chinese equivalent |
| **Structural challenges** | Long complex sentences, nested clauses | Break into breath groups, reorder |
| **Cultural references** | Events, people, products unknown in China | Translate concept or add note |
| **Wordplay/humor** | Puns, irony, sarcasm | Translate meaning, note wordplay if needed |

Record each challenge:
```
- [location/passage] → [challenge type] → [suggested approach]
- Ch3 "the elephant in the room" → idiom → "房间里的大象" is now understood in Chinese, can keep literal
- Ch7 baseball metaphor extended → cultural → translate the CONCEPT (teamwork/strategy), not the sport
```

### Analysis file format
```
# [Book Title] — 翻译分析

## 内容概要
[Summary, author, audience, purpose]

## 术语表
| English | Chinese | Notes |
|---------|---------|-------|
| ... | ... | ... |

## 语气与风格
- 语域：[formal/conversational/academic/...]
- 叙事视角：[first-person/third-person/...]
- 特征：[humor/metaphors/cultural-references/...]
- 建议翻译风格：[style preset]

## 翻译难点
- [passage] → [type] → [approach]
- ...
```

---

## Step R2: Initial Draft

Translate the full content following the analysis. Save to `[chapter]-draft.md`.

### Process
1. Read the analysis file (Step R1 output) — this is your translation brief
2. Read the source PDF pages
3. Translate paragraph by paragraph, applying:
   - The terminology table from analysis (be consistent)
   - The chosen style preset
   - All translation principles from SKILL.md
   - The Translation Challenges Map from analysis
4. Output in bilingual interleaved format

### Draft quality bar
- Every sentence translated? ✓
- Terminology consistent with analysis? ✓
- Natural Chinese (no obvious translation-ese)? ✓ (but minor awkwardness is expected — that's what review is for)
- All formatting preserved? ✓

### Translator's notes in draft
During drafting, mark anything you're unsure about with inline notes:
```
中文翻译文本。（**待确认：此处"xxx"译法是否准确？**）
```

These will be resolved during review.

---

## Step R3: Critical Review

**CRITICAL**: This is diagnosis only — do NOT rewrite yet. Save to `[chapter]-critique.md`.

Read the draft against the original with three lenses:

### Lens 1: Accuracy (准确性)
Compare every paragraph against the original:
- Flag any facts, numbers, dates, proper nouns that don't match
- Flag content accidentally added, omitted, or altered
- Check terminology consistency against the analysis glossary
- Verify every English sentence has a corresponding Chinese sentence

### Lens 2: Native Voice (中文自然度)
This is the most important lens. Flag every sentence that reads as "translated" rather than "written."

**The 6 red flags of Europeanized Chinese:**
1. **被字句泛滥**: Where the English passive could be translated more naturally
2. **不必要的连接词**: 因为...所以/虽然...但是/当...的时候 — where context already makes the logic clear
3. **定语堆叠**: Long pre-modifiers that should be split into clauses
4. **之一的滥用**: "one of the most..." over-translated as 最...之一
5. **的的的**: Three or more 的 in one sentence
6. **名词化过度**: "the implementation of" → ...的实施 instead of 实施... (verb)

**Additional checks:**
- Metaphors translated literally into nonsensical Chinese
- Emotional tone flattened or shifted
- Sentences that are grammatically correct but "feel foreign"
- Identical sentence structures repeated (monotonous rhythm)

### Lens 3: Cultural Adaptation (文化适配)
- Are translator's notes accurate, concise, genuinely helpful?
- Any missed comprehension gaps that need notes?
- Any over-annotations on obvious terms?
- Do cultural references work for a Chinese reader?
- Were translation strategies from the analysis actually followed?

### Critique file format
```
# [Chapter] — 审校意见

## 准确性
- [MUST FIX] [location]: [what's wrong — wrong number / missing sentence / inconsistent term]
- [MUST FIX] [location]: [issue]

## 中文自然度
- [location]: [current phrasing] → [why it reads as translation-ese] → [建议: suggested fix]
- [location]: [被字句可改] → [建议]
- [location]: [定语过长] → [建议拆分为短句]

## 文化适配
- [location]: [term/reference] → [current approach is fine / needs adjustment]
- [location]: [应加译注] → [suggested note]

## 总结
- 准确性问题：X 处必须修正
- 表达问题：Y 处建议修改
- 整体评价：[brief assessment]
```

---

## Step R4: Revision

Apply ALL findings from the critique. Save to `[chapter]-revision.md`.

### Process
1. Read both `[chapter]-draft.md` and `[chapter]-critique.md`
2. Fix every accuracy issue flagged as MUST FIX
3. Rewrite flagged unnatural expressions — this is where you turn "translated Chinese" into "real Chinese"
4. Adjust translator's notes as recommended
5. Improve flow between paragraphs

### Revision quality bar
- All MUST FIX items resolved? ✓
- The text now reads as if written in Chinese originally? ✓
- No remaining translation-ese? ✓
- Consistent voice and terminology? ✓

---

## Step R5: Polish

Final pass for publication quality. Save final to `[chapter]-chinese.md`.

### Polish checklist
1. **Read aloud test**: Read the entire translation silently — does every sentence flow as native Chinese?
2. **Transitions**: Are paragraph transitions smooth? Any abrupt topic shifts?
3. **Voice consistency**: Does the narrative voice stay consistent throughout?
4. **Terminology final check**: Any inconsistent term usage across paragraphs?
5. **Formatting**: Are all headings, blockquotes, and separators correct?
6. **Rhythm**: Mix of long and short sentences? No monotonous patterns?

### After polish
Show the user a brief summary:
```
精翻完成：[Chapter Title]
- 准确性问题修正：X 处
- 表达优化：Y 处
- 输出文件：[path]
```

---

## Chunked Refined Translation (for long chapters)

When a single chapter exceeds ~3000 English words, apply the refined workflow in chunks:

1. **Analyze once** for the entire chapter (Step R1)
2. **Draft in chunks**: split chapter into ~3000-word chunks, translate each chunk sequentially (not parallel — sequential ensures voice consistency), save merged draft
3. **Review the merged draft** (Step R3) — this is where cross-chunk consistency is validated
4. **Revise the full chapter** (Step R4)
5. **Polish the full chapter** (Step R5)
6. **Cross-chunk check**: terminology, narrative flow, transitions at chunk boundaries

---

## Subagent Usage

When the Agent tool is available and a chapter is long enough to benefit from parallel translation:

1. Main agent does analysis (Step R1) for the entire chapter
2. Main agent splits content into chunks
3. Spawn one subagent per chunk, all in parallel, each receiving:
   - The analysis file (shared context: glossary, style, challenges)
   - Its chunk of source text
   - Instruction: translate this chunk following the analysis
4. Main agent merges all translated chunks in order → draft (Step R2)
5. Main agent does review (Step R3), revision (Step R4), polish (Step R5) alone — these require holistic judgment

Subagents only do the initial draft (Step R2). The main agent owns quality.
