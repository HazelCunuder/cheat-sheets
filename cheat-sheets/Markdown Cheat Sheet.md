# Markdown Cheat Sheet

Markdown is a lightweight markup language that allows you to format text easily using a plain-text editor. It is commonly used for writing documentation, README files, and formatting content on platforms like GitHub, Reddit, and Stack Overflow.

## Table of Content

* [Basic Syntax](#basic-syntax)
* [Lists](#lists)
* [Tables](#tables)
* [Blockquotes](#blockquotes)
* [Code Blocks](#code-blocks)
* [Horizontal rules](#horizontal-rule)
* [Task Lists](#task-lists-github-flavored-markdown)

## Basic Syntax

| Syntax | Description | Example |
|--------|-------------|---------|
| `# Heading 1` | Large heading | `# This is an H1` |
| `## Heading 2` | Medium heading | `## This is an H2` |
| `### Heading 3` | Small heading | `### This is an H3` |
| `**bold**` | Bold text | `**This is bold**` → **This is bold** |
| `*italic*` | Italic text | `*This is italic*` → *This is italic* |
| `~~strikethrough~~` | Strikethrough text | `~~This is struck through~~` → ~~This is struck through~~ |
| `` `code` `` | Inline code | `` `This is code` `` → `This is code` |
| `[Link](http://example.com)` | Hyperlink | `[Google](https://google.com)` → [Google](https://google.com) |
| `![Alt text](image.jpg)` | Image | `![Logo](logo.png)` |

## Lists

### Unordered Lists

```plain
- Item 1
- Item 2
  - Sub-item 1
  - Sub-item 2
```

* Item 1
* Item 2
  * Sub-item 1
  * Sub-item 2

### Ordered Lists

```plain
1. First item
2. Second item
   1. Sub-item 1
   2. Sub-item 2
```

1. First item
2. Second item
   1. Sub-item 1
   2. Sub-item 2

## Tables

```plain
| Column 1 | Column 2 | Column 3 |
|----------|----------|----------|
| Row 1A   | Row 1B   | Row 1C   |
| Row 2A   | Row 2B   | Row 2C   |
```

| Column 1 | Column 2 | Column 3 |
|----------|----------|----------|
| Row 1A   | Row 1B   | Row 1C   |
| Row 2A   | Row 2B   | Row 2C   |

## Blockquotes

```plain
> This is a blockquote
>> spanning multiple lines.
```

> This is a blockquote
>> spanning multiple lines.

## Code Blocks

\`\`\`python

print("Hello, World!")

\`\`\`

```python

print("Hello, World!")

```

## Horizontal Rule

```plain
---
```

---

## Task Lists (GitHub Flavored Markdown)

```plain
- [x] Task 1
- [ ] Task 2
- [ ] Task 3
```

* [x] Task 1
* [ ] Task 2
* [ ] Task 3
