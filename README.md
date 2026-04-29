# PDF Translator Skill for Claude Code

一键将英文PDF书籍翻译为流畅中文的Claude Code技能，支持三种翻译模式（速译/标准/精翻），五种风格预设。

## 一键安装

```bash
git clone https://github.com/Cuimao777/pdf-translator-skill.git ~/.claude/skills/pdf-translator
```

或者安装到指定项目：

```bash
git clone https://github.com/YOUR_USERNAME/pdf-translator-skill.git /path/to/project/.claude/skills/pdf-translator
```

安装后在Claude Code中直接说"翻译这个PDF"即可触发。

## 触发词

`翻译` `汉化` `英译中` `PDF翻译` `精翻` `速译` `translate this book`

## 三种模式

| 模式 | 触发词 | 适合场景 |
|------|--------|----------|
| Quick 速译 | 快翻、速译 | 快速浏览、短篇内容 |
| Normal 标准 | 默认、翻译 | 大多数章节、博客、通用内容 |
| Refined 精翻 | 精翻、精细翻译 | 出版级输出、最终交付 |

## 五种风格

- `storytelling` 叙事流畅 — 小说、回忆录、叙事非虚构
- `academic` 学术严谨 — 学术著作、教科书
- `literal` 逐句忠实 — 技术手册、法律文件
- `elegant` 文采典雅 — 文学小说、诗歌
- `conversational` 口语自然 — 对话密集、自助类书籍

## 核心原则

信（忠实原文）→ 达（中文流畅）→ 雅（文化适配）
