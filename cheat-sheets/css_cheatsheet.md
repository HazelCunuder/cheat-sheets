# 🎨 CSS Cheatsheet — The Essentials

## ✅ Basic Syntax

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

- **Selector:** Targets the HTML element(s)
- **Property:** The style you want to change
- **Value:** The setting for the property
- **Declaration Block:** `{ property: value; }`

## 🛠️ 4 Ways to Use CSS in HTML

1. **Inline CSS**

```zsh
<p style="color: red;">Hello</p>
```

2. **Internal CSS (Embedded)**

```zsh
<style>
  p {
    color: green;
  }
</style>
```

3. **External CSS (Recommended)**

```zsh
<link rel="stylesheet" href="styles.css" />
```

4. **Imported CSS**

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

- Content → Actual text/images
- Padding → Space inside the element
- Border → Outline around padding + content
- Margin → Space outside the element

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

## Flexbox Guide

### What is Flexbox?

Flexbox (Flexible Box Layout) is a CSS layout model designed to help arrange elements efficiently inside a container, even when their sizes are dynamic. It allows for easy alignment, distribution, and spacing of items, making it a powerful tool for responsive web design.

### How Flexbox Works

Flexbox consists of a **flex container** and **flex items**. When you apply `display: flex` to a container, all of its direct children become flex items and are automatically aligned according to the specified flex properties.

#### Enabling Flexbox

To use Flexbox, set the container's `display` property to `flex` or `inline-flex`:

```css
.container {
  display: flex; /* or inline-flex */
}
```

### Flex Container Properties

The flex container controls how its child elements (flex items) behave. The key properties are:

#### 1. `flex-direction`

Defines the main axis along which items are placed:

```css
.container {
  flex-direction: row; /* default */
  flex-direction: row-reverse;
  flex-direction: column;
  flex-direction: column-reverse;
}
```

#### 2. `justify-content`

Aligns items along the main axis:

```css
.container {
  justify-content: flex-start; /* default */
  justify-content: flex-end;
  justify-content: center;
  justify-content: space-between;
  justify-content: space-around;
  justify-content: space-evenly;
}
```

#### 3. `align-items`

Aligns items along the cross axis:

```css
.container {
  align-items: stretch; /* default */
  align-items: flex-start;
  align-items: flex-end;
  align-items: center;
  align-items: baseline;
}
```

#### 4. `align-content`

Controls spacing between multiple rows in a flex container with `flex-wrap: wrap`:

```css
.container {
  align-content: flex-start;
  align-content: flex-end;
  align-content: center;
  align-content: space-between;
  align-content: space-around;
  align-content: space-evenly;
}
```

#### 5. `flex-wrap`

Determines whether flex items should wrap to the next row:

```css
.container {
  flex-wrap: nowrap; /* default */
  flex-wrap: wrap;
  flex-wrap: wrap-reverse;
}
```

#### 6. `gap`

Defines space between flex items:

```css
.container {
  gap: 10px;
}
```

### Flex Item Properties

Each flex item can be individually controlled using these properties:

#### 1. `flex-grow`

Defines how much a flex item should grow relative to others:

```css
.item {
  flex-grow: 1; /* Takes up equal space */
}
```

#### 2. `flex-shrink`

Defines how much an item should shrink if needed:

```css
.item {
  flex-shrink: 1; /* default */
  flex-shrink: 0; /* Prevent shrinking */
}
```

#### 3. `flex-basis`

Sets the initial size of an item before flex-grow/shrink are applied:

```css
.item {
  flex-basis: 100px;
}
```

#### 4. `flex`

A shorthand for `flex-grow`, `flex-shrink`, and `flex-basis`:

```css
.item {
  flex: 1 1 auto; /* default */
}
```

#### 5. `align-self`

Overrides `align-items` for a specific item:

```css
.item {
  align-self: flex-start;
  align-self: flex-end;
  align-self: center;
  align-self: baseline;
  align-self: stretch;
}
```
