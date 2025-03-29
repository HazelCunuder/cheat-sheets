# Flexbox Guide

## What is Flexbox?

Flexbox (Flexible Box Layout) is a CSS layout model designed to help arrange elements efficiently inside a container, even when their sizes are dynamic. It allows for easy alignment, distribution, and spacing of items, making it a powerful tool for responsive web design.

## How Flexbox Works

Flexbox consists of a **flex container** and **flex items**. When you apply `display: flex` to a container, all of its direct children become flex items and are automatically aligned according to the specified flex properties.

### Enabling Flexbox

To use Flexbox, set the container's `display` property to `flex` or `inline-flex`:

```css
.container {
  display: flex; /* or inline-flex */
}
```

## Flex Container Properties

The flex container controls how its child elements (flex items) behave. The key properties are:

### 1. `flex-direction`

Defines the main axis along which items are placed:

```css
.container {
  flex-direction: row; /* default */
  flex-direction: row-reverse;
  flex-direction: column;
  flex-direction: column-reverse;
}
```

### 2. `justify-content`

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

### 3. `align-items`

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

### 4. `align-content`

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

### 5. `flex-wrap`

Determines whether flex items should wrap to the next row:

```css
.container {
  flex-wrap: nowrap; /* default */
  flex-wrap: wrap;
  flex-wrap: wrap-reverse;
}
```

### 6. `gap`

Defines space between flex items:

```css
.container {
  gap: 10px;
}
```

## Flex Item Properties

Each flex item can be individually controlled using these properties:

### 1. `flex-grow`

Defines how much a flex item should grow relative to others:

```css
.item {
  flex-grow: 1; /* Takes up equal space */
}
```

### 2. `flex-shrink`

Defines how much an item should shrink if needed:

```css
.item {
  flex-shrink: 1; /* default */
  flex-shrink: 0; /* Prevent shrinking */
}
```

### 3. `flex-basis`

Sets the initial size of an item before flex-grow/shrink are applied:

```css
.item {
  flex-basis: 100px;
}
```

### 4. `flex`

A shorthand for `flex-grow`, `flex-shrink`, and `flex-basis`:

```css
.item {
  flex: 1 1 auto; /* default */
}
```

### 5. `align-self`

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

## Example: Simple Flexbox Layout

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Flexbox Example</title>
  <style>
    .container {
      display: flex;
      justify-content: space-between;
      align-items: center;
      background-color: #f4f4f4;
      padding: 10px;
    }
    .item {
      background-color: #3498db;
      color: white;
      padding: 20px;
      margin: 5px;
      flex: 1;
      text-align: center;
    }
  </style>
</head>
<body>
  <div class="container">
    <div class="item">Item 1</div>
    <div class="item">Item 2</div>
    <div class="item">Item 3</div>
  </div>
</body>
</html>
```
