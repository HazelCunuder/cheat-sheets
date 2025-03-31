# Grid layout Cheat-sheet

## What is the grid layout

The Grid layout is one of the other CSS display module, along with flexbox. It is similar to tables in the sense that it also works with columns and rows, however, it is much more advanced as you are able to do many more things with the Grid layout than just HTML tables.

## Table of Content

## Grid Container Properties

| Property | Description |
|----------|------------|
| `display: grid;` | Defines a container as a grid |
| `grid-template-columns` | Defines column sizes and number of columns |
| `grid-template-rows` | Defines row sizes and number of rows |
| `grid-template-areas` | Defines named grid areas |
| `grid-column-gap` / `column-gap` | Sets space between columns |
| `grid-row-gap` / `row-gap` | Sets space between rows |
| `gap` | Shorthand for `row-gap` and `column-gap` |
| `align-items` | Aligns items vertically within their grid cells |
| `justify-items` | Aligns items horizontally within their grid cells |
| `place-items` | Shorthand for `align-items` and `justify-items` |

## Grid Item Properties

| Property | Description |
|----------|------------|
| `grid-column` | Defines start and end column positions |
| `grid-row` | Defines start and end row positions |
| `grid-area` | Assigns an item to a named grid area |
| `align-self` | Aligns a single item vertically |
| `justify-self` | Aligns a single item horizontally |
| `place-self` | Shorthand for `align-self` and `justify-self` |

## Common Grid Values

| Value | Description |
|-------|------------|
| `auto` | Automatically size rows/columns based on content |
| `fr` | Fractional unit for flexible sizing |
| `repeat(n, value)` | Creates repeating columns/rows |
| `minmax(min, max)` | Sets a flexible size range |
| `1fr 2fr` | First column takes 1 fraction, second column takes 2 fractions |
| `grid-column: span N` | Span item across N columns |

## Example: Basic Grid Layout

```css
.container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: auto;
  gap: 10px;
}
.item {
  background: lightblue;
  padding: 20px;
  text-align: center;
}
```

```html
<div class="container">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
</div>
```
