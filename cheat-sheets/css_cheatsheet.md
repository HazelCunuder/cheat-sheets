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
