# English→Chinese Translation Reference Guide

Detailed patterns, pitfalls, and glossaries for producing natural Chinese translations from English text.

## Table of Contents
1. [Europeanized Chinese Detection](#europeanized-chinese)
2. [Sentence Structure Transformation](#sentence-structure)
3. [Common Patterns & Fixes](#common-patterns)
4. [Literary & Fiction Translation](#literary)
5. [Non-Fiction & Academic](#non-fiction)
6. [Business & Technology](#business)
7. [Dialogue Translation](#dialogue)
8. [Idioms & Cultural References](#idioms)

---

## 1. Europeanized Chinese Detection (欧化中文检测) {#europeanized-chinese}

The most common problem in English→Chinese translation is 欧化中文 — Chinese that follows English grammar structures and "feels foreign." This section is a self-diagnostic toolkit. After translating, run through these checks.

### The Six Red Flags

#### Red Flag 1: 被字句泛滥 (Passive Voice Overuse)

English uses passive voice extensively. Chinese uses 被 far less — it often carries negative connotations (被害、被打、被骗).

```
EN: The project was completed on time.
BAD: 项目被按时完成了。
GOOD: 项目按时完成了。

EN: He was elected chairman.
BAD: 他被选为主席。
GOOD: 他当选为主席。

EN: The policy was widely criticized.
BAD: 政策被广泛批评。
GOOD: 政策受到广泛批评。/ 舆论普遍批评这一政策。
```

**Replace 被 with:**
- 由 (agent): "由专家组撰写"
- 受/受到 (received): "受到欢迎", "受到质疑"
- 得到/获得 (positive): "得到认可", "获得批准"
- 遭/遭遇 (negative): "遭到反对"
- Topic-comment: "问题解决了" (not "问题被解决了")
- Active with generic subject: "人们认为", "有人指出"

#### Red Flag 2: 不必要的连接词 (Connective Overuse)

English requires explicit logical connectors. Chinese often lets context do the work.

```
EN: Because it was raining, we stayed inside.
BAD: 因为下雨了，所以我们待在屋里。
GOOD: 下雨了，我们待在屋里。

EN: Although he tried hard, he failed.
BAD: 虽然他非常努力，但是他还是失败了。
GOOD: 他非常努力，还是失败了。

EN: When I arrived, he was already there.
BAD: 当我到达的时候，他已经在那里了。
GOOD: 我到了，他已经在了。

EN: If you need help, let me know.
BAD: 如果你需要帮助，请告诉我。
GOOD: 需要帮忙就说。
```

**Common English connectives that Chinese often drops:**
- "When..." → 当...的时候 → Usually just context or 等/到
- "Because... so..." → 因为...所以... → Often just context
- "Although... but..." → 虽然...但是... → 虽然...还是 or just context
- "If... then..." → 如果...那么... → 如果...就 or just ...的话
- "Not only... but also..." → 不仅...而且... → 既...又 or restructure

**Rule of thumb**: If removing the connective doesn't change the meaning, remove it.

#### Red Flag 3: 定语堆叠过长 (Long Pre-modifiers)

English can stack long clauses before a noun. Chinese cannot.

```
EN: The man who had been waiting for three hours in the rain outside the station finally gave up.
BAD: 那个在车站外面的雨里等了三个小时的男人终于放弃了。
GOOD: 那人在车站外冒着雨，等了三个钟头，终于放弃了。

EN: A comprehensive framework for the analysis of complex systems that integrates multiple methodological approaches.
BAD: 一个整合了多种方法论的复杂系统分析的综合性框架。
GOOD: 一个综合性框架，整合了多种方法论，用以分析复杂系统。
```

**Strategy**: When a Chinese noun phrase exceeds ~15 characters, split:
1. Introduce the topic first
2. Add descriptive clauses after
3. Use commas to create breath groups

#### Red Flag 4: 之一的滥用 (Overuse of "One of the Most")

```
EN: One of the most important discoveries of the 20th century.
BAD: 20世纪最重要的发现之一。
GOOD: 20世纪极为重要的一个发现。/ 20世纪影响深远的发现。
```

"之一" is grammatically correct but rhythmically weak. Reserve for cases where the "one among many" meaning is essential.

#### Red Flag 5: 的密度过高 (的 Density)

If three or more 的 appear in one sentence, restructure.

```
EN: The new policy of the company's management team's decision
BAD: 公司管理层的新的政策的决定
GOOD: 公司管理层出台的新政策决定 / 公司管理层做出的新决策
```

**Fixes:**
- Drop possessive 的 when obvious: "我爸爸" not "我的爸爸"
- Replace modifier 的 with 之 in formal register
- Restructure into verb phrases

#### Red Flag 6: 名词化过度 (Over-Nominalization)

English academic writing nominalizes verbs. Chinese prefers verbs.

```
EN: The implementation of the strategy resulted in the improvement of efficiency.
BAD: 策略的实施带来了效率的提升。
GOOD: 实施这一策略后，效率提升了。

EN: The analysis of the data led to the discovery of a pattern.
BAD: 对数据的分析导致了一个模式的发现。
GOOD: 分析数据后，发现了一个模式。

EN: His explanation of the concept was clear.
BAD: 他对概念的讲解是清晰的。
GOOD: 他把这个概念讲得很清楚。
```

**Pattern**: "the [noun] of [X]" → "[verb] [X]" in Chinese.

### Self-Diagnostic Flow

After translating a paragraph, scan quickly:
1. Any 被 I can replace? → Replace with 由/受/得到 or active voice
2. Can I remove any 因为...所以/虽然...但是/当...的时候? → Try dropping them
3. Any noun phrase with 的 repeated? → Split into clauses
4. Any 之一 I can rephrase? → Use 极为/非常/...得很
5. Any "...的..." nominalization? → Use verb instead

---

## 2. Sentence Structure Transformation {#sentence-structure}

### English → Chinese structural differences

**English**: Subject-Verb-Object, heavy use of subordination, long sentences with embedded clauses.
**Chinese**: Topic-Comment, prefers coordination over subordination, shorter breath groups.

### Strategy: Break and Rebuild

When facing a long English sentence with multiple clauses:

1. Identify the core meaning
2. Break into Chinese breath groups (意群) of 7-15 characters each
3. Reorder groups into natural Chinese topic→comment flow
4. Add or remove connectives as needed for Chinese rhythm

**Example:**
```
EN: The rapid advancement of artificial intelligence,
    which has transformed industries ranging from healthcare
    to finance, has raised important questions about the future
    of work that policymakers are only beginning to address.

BAD: 人工智能的快速发展，它已经改变了从医疗到金融的各个行业，
      引发了政策制定者才刚刚开始应对的关于未来工作的重要问题。

GOOD: 人工智能突飞猛进，深刻改变了医疗、金融等各行各业，
      未来的工作形态将何去何从？政策制定者才刚刚开始正视这个问题。
```

### Passive Voice Handling

English passive → Chinese alternatives:

| English | Avoid | Use |
|---------|-------|-----|
| "was built by" | 被建造 | 由...建造 / ...而成 |
| "is considered" | 被认为 | 人们认为 / 一般认为 |
| "can be seen" | 可以被看到 | 可见 / 看得出 |
| "was discovered that" | 被发现 | 据发现 / 人们发现 |
| "it is said that" | 它被说 | 据说 / 有人说 |

**Key insight**: Chinese uses 被 (bèi) far less than English uses passive voice. 被 often carries negative connotations (被偷、被打). For neutral situations, use:
- 由 (yóu) for agent: "由专家撰写"
- 受 (shòu) for received action: "受欢迎"
- 得到/获得 for positive: "得到认可"
- Topic-comment structure: "这个问题已经解决了"
- Active voice with generic subject: "人们认为"

---

## 3. Common Patterns & Fixes {#common-patterns}

### "It is... that..." / "It is... to..."

```
EN: It is important to note that...
BAD: 重要的是要注意到...
GOOD: 值得注意的是... / 必须指出...
```

### "One of the most..."

```
EN: One of the most influential books of the century
BAD: 本世纪最有影响力的书之一
GOOD: 本世纪极有影响力的一本书 / 本世纪影响深远的一部著作
```

### "There is/are..."

```
EN: There are many reasons why this approach fails
BAD: 有很多原因为什么这种方法会失败
GOOD: 这种方法之所以失败，原因很多
```

### "The fact that..."

```
EN: The fact that he survived surprised everyone
BAD: 他幸存下来的事实让所有人惊讶
GOOD: 他竟然活下来了，人人都很吃惊
```

### "Not only... but also..."

```
EN: She not only wrote the book but also illustrated it
BAD: 她不仅写了这本书，而且还画了插图
GOOD: 她既写了这本书，又亲手配了插图
```

### "As... as..."

```
EN: The project was as ambitious as it was expensive
BAD: 这个项目既雄心勃勃又昂贵
GOOD: 这个项目耗资巨大，同样野心勃勃
```

### English adverbs → Chinese complements

English -ly adverbs often become Chinese complements (补语):

```
EN: He walked slowly → 他走得很慢
EN: She explained clearly → 她解释得很清楚
EN: The economy grew rapidly → 经济增长迅猛
```

### English possessives → Chinese topic structure

```
EN: His eyes were blue → 他眼睛是蓝的 (not 他的眼睛是蓝的)
EN: The city's population grew → 城市人口增长了
```

---

## 4. Literary & Fiction Translation {#literary}

### Dialogue

- Chinese dialogue uses different punctuation: 「」 or "" — be consistent
- Add 啊, 吧, 呢, 嘛 for natural speech rhythm
- Use contractions: 不用→甭, 什么→啥, 怎么→咋 (only for informal characters)
- Render dialects/accents by word choice, not phonetic distortion
- Preserve character voice: formal vs casual, educated vs uneducated

### Description & Imagery

- Chinese literary tradition values 意境 (artistic conception) — evoke mood, not just detail
- Use four-character phrases (四字格) for rhythm: 阳光明媚, 微风拂面, 落叶缤纷
- Translate sensory details fully — smells, sounds, textures matter
- When an English metaphor is extended over several sentences, keep the same metaphor system in Chinese

### Narrative Voice

- Distinguish narrator voice from character voice in Chinese
- Free indirect discourse: blend subtly, as in the original
- Stream of consciousness: preserve the fragmented, associative quality

### Tense & Time

Chinese has no grammatical tense. Use:
- Time words: 曾经, 已经, 正在, 将要
- Aspect markers: 了, 过, 着 (use sparingly)
- Context: let surrounding sentences establish time frame

```
EN: He had been waiting for hours when she finally arrived
GOOD: 他已经等了好几个钟头，她终于来了
```

---

## 5. Non-Fiction & Academic {#non-fiction}

### Terminology

- Use established Chinese academic terms
- On first use, consider: 中文术语（英文原词）
- Be consistent throughout the entire translation

### Argument Structure

- Preserve logical connectors but adapt to Chinese: "therefore" → 因此, "however" → 然而/不过, "moreover" → 此外/而且
- English academic writing uses many hedging phrases ("it might be argued that", "to some extent") — don't over-translate these into heavy Chinese; keep the academic caution but use lighter Chinese equivalents

### Citations

- Keep citations exactly as-is: "(Smith, 2020, p. 42)"
- Translate footnote text but keep footnote numbers

---

## 6. Business & Technology {#business}

### Business Jargon

```
EN: "low-hanging fruit" → 容易摘到的果子 → 短期见效的事
EN: "move the needle" → 移动指针 → 产生实质影响
EN: "circle back" → 绕回来 → 回头再议
EN: "deep dive" → 深潜 → 深入探讨
EN: "bandwidth" → 带宽 → 精力/人手
```

### Tech Terminology

- Widely-used English tech terms can stay in English: API, CPU, SaaS
- But prefer Chinese when standard: 人工智能 (not AI), 机器学习 (not ML), 数据库 (not database)
- Translate UX copy thoughtfully — it's what users see

---

## 7. Dialogue Translation {#dialogue}

### Key principles

1. **Character voice**: Each character should sound distinct in Chinese. A professor and a teenager must use different vocabulary and sentence patterns.
2. **Natural speech**: Read the Chinese dialogue aloud in your head. Does it sound like something a real Chinese person would say?
3. **Subtext**: Preserve what's left unsaid. Chinese often implies meaning through context — don't over-explain.
4. **Interjections**: Map English interjections to natural Chinese ones:
   - "Oh!" → 哦！/ 哎呀！
   - "Well..." → 嗯...
   - "Hmm" → 唔...
   - "Wow!" → 哇！/ 天哪！
   - "Oops" → 哎呀 / 糟了
   - "Ugh" → 唉 / 啧

### Addressing & Politeness

- English "you" → 你 (informal) or 您 (formal) depending on relationship
- Titles: Mr. → 先生, Mrs./Ms. → 女士, Dr. → 博士/医生
- Family terms: Use Chinese kinship system (大哥, 阿姨, 叔叔) when appropriate

---

## 8. Idioms & Cultural References {#idioms}

### When to find Chinese equivalents

| Situation | Approach |
|-----------|----------|
| Universal concept with Chinese equivalent | Use the Chinese idiom |
| English-specific cultural reference | Translate + brief explanation |
| Bible/literary allusion | Check if there's a standard Chinese translation |
| Humor/pun | Translate meaning + note wordplay |

### Common English Idioms → Chinese

```
"break the ice" → 打破沉默 / 破冰
"bite the bullet" → 硬着头皮
"call it a day" → 收工 / 到此为止
"cut corners" → 偷工减料
"hit the nail on the head" → 一针见血
"kill two birds with one stone" → 一箭双雕 / 一举两得
"let the cat out of the bag" → 泄露天机 / 露馅
"once in a blue moon" → 千载难逢
"piece of cake" → 小菜一碟
"see eye to eye" → 看法一致 / 对眼
"speak of the devil" → 说曹操曹操到
"the last straw" → 最后一根稻草 / 忍无可忍
"under the weather" → 身体不适
```

### Sports/Military Metaphors in Business Writing

English business writing is full of sports and military metaphors. Chinese business writing uses fewer. Options:

1. Translate the concept (preferred): "step up to the plate" → 挺身而出
2. Keep if the metaphor is central to understanding
3. Use a Chinese business equivalent if one exists

```
"ballpark figure" → 大致数字 / 粗略估算
"game changer" → 颠覆性变革 / 改变格局
"level playing field" → 公平竞争环境
"hit the ground running" → 立刻上手
```

### What to NEVER translate literally

- Proper names (unless there's a standard translation)
- Brand names
- Code, formulas, URLs
- Legal disclaimers
- Copyright notices
