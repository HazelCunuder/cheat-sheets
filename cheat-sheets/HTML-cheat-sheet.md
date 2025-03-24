# HTML5 Cheatsheet

## HTML Basics

### Basic Structure

```zsh
<html>
    <head>
        <title>website title</title>
    </head>
        
    <body>
        content
    </body>
</html>
```

### Common Tags

| Tag | Description |
| --- | --- |
| `<h?> heading </h?>`| Heading (1-6, from big to small) |
| `<p> paragraph </p>` | Paragraph |
| `<b> bold </b>` | Makes text **bold** |
| `<i> italic </i>` | Makes text *italic* |
| `<a href="url"> link name </a>` | Create link to another page or site |
| `<div> ... </div>` | Divide page into sections |
| `<img src="filename.jpg or image link">` | Show an image |
| `<ul> <ol> <li>` | Create lists |
| `<br>` | Line Break |
| `<strong> ... </strong>` | Strong - shown as bold |
| `<em> ... </em>` | Emphasis - Shown as italics |

### Attributes

| Attribute | Description |
| --- | --- |
| `href` | Link to other page URL |
| `src` | Path to an image |
| `width` | Specify the width of an element |
| `height` | Specify the height of an element |
| `alt` | Create Alt text for an image |
| `lang` | Specify the page's language |
| `title` | Create a tooltip for an element |
| `style` | Add style for an element |

### Comments

You can add comments to your HTML code by doing the following:

```zsh
<!-- Insert your comment here -->
```

Adding Comments can be useful to describe what the code does *(or to reconsider your life choices)*.
You can also use them in order to debug our code by hiding a line at a time to find the broken code.

You can also hide more than one line using the comment tags.

```zsh
<!-- 
    <p>This is hidden</p>
    <p>And so is this</p>
-->
```

### The Family Tree

An HTML document is basically structured like a family tree, there are ancestors, parents, children, siblings, etc.

This structure can easily be explained with the following picture

![HTML Family Tree](https://www.tutorjoes.in/js_program/family_tree.jpg)
&copy; tutorjoes.in

### Semantics

Semantics elements are elements that clearly describe its meaning to both the browseer and the developer.

For example, `<img>` is a **sementic** element, because it clearly define its content.
Whereas `<div>` doesn't, making it **non-semantic**.

| Tag         | Description |
|------------|------------|
| `<article>`  | Defines independent, self-contained content |
| `<aside>`    | Defines content aside from the page content |
| `<details>`  | Defines additional details that the user can view or hide |
| `<figcaption>` | Defines a caption for a `<figure>` element |
| `<figure>`   | Specifies self-contained content, like illustrations, diagrams, photos, code listings, etc. |
| `<footer>`   | Defines a footer for a document or section |
| `<header>`   | Specifies a header for a document or section |
| `<main>`     | Specifies the main content of a document |
| `<mark>`     | Defines marked/highlighted text |
| `<nav>`      | Defines navigation links |
| `<section>`  | Defines a section in a document |
| `<summary>`  | Defines a visible heading for a `<details>` element |
| `<time>`     | Defines a date/time |

### Relative/Absolute Paths

When inserting a file inside of your html code, you will need to describe its path to your code. There are 2 ways to do this.

You can either write the full URL to a file if it has one, like this:

```zsh
<img src="https://external-preview.redd.it/HvRHG_yCXU8q5biZkkmv_ENnzgAaI-SH5NDYasF2yYo.png?width=640&crop=smart&format=pjpg&auto=webp&s=c0c7ced8f7f7cc400a66ce967baf2a9068ccb1bc">
```

The above example is an **absolute** path.

The other option, is to include the path to a file relative to the current page, this is the **relative** path.

In the following example, the file path points to a file in the images folder located at the root of the current web:

```zsh
<img src="/images/picture.jpg">
```

If possible, using relatives paths is a better option as they are not bound to an URL that is subject to change.
