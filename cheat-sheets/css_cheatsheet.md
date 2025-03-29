# 🎨 CSS Cheatsheet — The Essentials

## Table of Content

* [Basic Syntax](#basic-syntax)
* [🛠️ 4 Ways to Use CSS in HTML](#️-4-ways-to-use-css-in-html)
* [🎯 Selectors](#-selectors-class-id-universal-pseudo-classes-pseudo-elements)
* [🧩 How to Apply CSS to Elements](#-how-to-apply-css-to-elements)
* [📦 The Box Model](#-the-box-model)
* [🚀 Positioning in CSS](#-positioning-in-css)
* [⚖️ Specificity](#️-specificity--which-rule-wins)

## Basic Syntax

```css
selector {
  property: value;
}
```

Example:

```css
p {
  color: blue;
  font-size: 16px;
}
```

* **Selector:** Targets the HTML element(s)
* **Property:** The style you want to change
* **Value:** The setting for the property
* **Declaration Block:** `{ property: value; }`

## 🛠️ 4 Ways to Use CSS in HTML

* **Inline CSS**

```zsh
<p style="color: red;">Hello</p>
```

* **Internal CSS (Embedded)**

```zsh
<style>
  p {
    color: green;
  }
</style>
```

* **External CSS (Recommended)**

```zsh
<link rel="stylesheet" href="styles.css" />
```

* **Imported CSS**

```css
@import url("styles.css");
```

## 🎯 Selectors: Class, ID, Universal, Pseudo-classes, Pseudo-elements

| Selector Type       | Syntax                | Example                         | Purpose                                                              |
|--------------------|---------------------|-------------------------------|--------------------------------------------------------------------|
| **Class**          | `.classname`        | `.card { color: black; }`     | Targets multiple elements sharing the same class                  |
| **ID**             | `#idname`          | `#header { background: blue; }` | Targets ONE unique element                                       |
| **Universal**      | `*`                | `* { margin: 0; }`            | Targets ALL elements                                              |
| **Pseudo-class**   | `selector:pseudo`  | `a:hover { color: red; }`     | Applies styles to an element in a specific state                  |
| **Pseudo-element** | `selector::pseudo` | `p::first-line { color: red; }`| Targets part of an element’s content                              |

## 🧩 How to Apply CSS to Elements

```css
/* Tag name selector */
h1 {
  color: navy;
}

/* Class selector */
.btn {
  padding: 10px;
}

/* ID selector */
#main {
  width: 100%;
}

/* Group multiple selectors */
h1, h2, h3 {
  margin-bottom: 1rem;
}

/* Descendant selector */
nav a {
  text-decoration: none;
}
```

## 📦 The Box Model

```zsh
+-------------------------------+
|         Margin (outside)      |
| +---------------------------+ |
| |      Border               | |
| | +-----------------------+ | |
| | |   Padding            | | |
| | | +-------------------+ | | |
| | | |   Content        | | | |
| | | +-------------------+ | | |
| | +-----------------------+ | |
| +---------------------------+ |
+-------------------------------+
```

**Layers:**

* Content → Actual text/images
* Padding → Space inside the element
* Border → Outline around padding + content
* Margin → Space outside the element

Example:

```css
.card {
  margin: 10px;
  padding: 20px;
  border: 1px solid black;
}
```

## 🚀 Positioning in CSS

| Value         | Meaning                                                             |
|--------------|---------------------------------------------------------------------|
| `static`    | Default. Normal document flow.                                       |
| `relative`  | Positioned **relative to itself**.                                   |
| `absolute`  | Positioned **relative to closest positioned ancestor**.              |
| `fixed`     | Positioned relative to **viewport** — stays on screen when scrolling.|
| `sticky`    | Scrolls until it reaches a threshold, then sticks.                  |

Example:

```css
.box {
  position: absolute;
  top: 50px;
  left: 100px;
}
```

## ⚖️ Specificity — Which Rule Wins?

**Order of Power:**

```zsh
!important > Inline style > ID selector > Class/Attribute/Pseudo-class > Tag/Pseudo-element > Universal (*)
```

**Quick Specificity Points:**

```zsh
Inline Style: 1000 pts
ID: 100 pts
Class/Attribute/Pseudo-class: 10 pts
Element/Pseudo-element: 1 pt
Universal (*): 0 pt
```

**Example:**

```css
/* Specificity: 0,0,0,1 */
h1 {
  color: blue;
}

/* Specificity: 0,0,1,0 */
.title {
  color: green;
}

/* Specificity: 0,1,0,0 */
#header {
  color: red;
}

/* Inline style */
<h1 style="color: yellow;">Hi</h1>
```

**The Result:**  
Yellow (inline style) wins, then `#header`, then `.title`, then `h1`.

---

**Bonus:**  
You can learn more at the [MDN CSS Guide](https://developer.mozilla.org/en-US/docs/Web/CSS).

---
