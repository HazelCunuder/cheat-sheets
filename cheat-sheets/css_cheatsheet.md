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
