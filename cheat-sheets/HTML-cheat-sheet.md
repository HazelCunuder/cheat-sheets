# HTML5 Cheatsheet

## HTML Role

HTML is a language used to build the basic structure of a web page. It stands for Hyper Text Markup Language, and is the standard language for building web pages.

Using different tags, it tells your browser how your page is structured and what to show.

It is the most basic of web languages and a must know for every aspiring web developer.

### HTML4 vs HTML5

| Feature            | HTML4                                          | HTML5                                          |
|--------------------|----------------------------------------------|----------------------------------------------|
| **Doctype**       | `<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">` | `<!DOCTYPE html>` (simplified) |
| **Multimedia**    | Uses `<object>`, `<embed>`, and third-party plugins (e.g., Flash) | Native support for `<audio>` and `<video>` elements |
| **Semantic Elements** | Limited, relies heavily on `<div>` and `<span>` | Introduces `<article>`, `<section>`, `<header>`, `<footer>`, etc. |
| **Form Enhancements** | Basic form elements; validation requires JavaScript | New input types (`email`, `date`, `number`), attributes (`placeholder`, `required`) |
| **Canvas & Graphics** | Requires third-party plugins like Flash | Introduces `<canvas>` for drawing and native SVG support |
| **Storage**       | Relies on cookies for client-side storage | Supports `localStorage` and `sessionStorage` for persistent storage |
| **APIs**         | Limited built-in APIs | New APIs like Geolocation, WebSockets, Web Storage, and Drag-and-Drop |
| **JavaScript Support** | Requires external libraries for many features | Enhanced JavaScript API support, including Web Workers and WebRTC |
| **Mobile Support** | Not designed with mobile in mind | Mobile-friendly, responsive, supports touch events |
| **Parsing Rules** | Strict, based on SGML | More flexible, error-handling improved |

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

| Tag         | Purpose | 🔎 Misuse Warning | Spec Link |
|------------|------------|------------|------------|
| `<!doctype>` | Declares HTML5 document type | None | [Doctype](https://developer.mozilla.org/en-US/docs/Web/HTML/Quirks_Mode_and_Standards_Mode) |
| `<html>` | Root element of the HTML document | Omitting `lang` attribute harms accessibility | [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html) |
| `<head>` | Contains metadata, title, styles, scripts | Should not contain visible content | [Head](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/head) |
| `<body>` | Contains all visible content | None | [Body](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body) |
| `<header>` | Introductory content for site or section | Misused when wrapping just headings without contextual content | [Header](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/header) |
| `<nav>` | Primary navigation links | Don't wrap every group of links; use only for major navigation | [Nav](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/nav) |
| `<main>` | Main, unique content of the document | **Only one per page**; don't nest in `<article>` or `<section>` | [Main](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/main) |
| `<section>` | Thematically grouped content with heading | Misused as a generic container; only use with heading | [Section](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/section) |
| `<article>` | Self-contained, distributable content | Misused when used solely as a layout wrapper | [Article](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/article) |
| `<aside>` | Content tangential to main content | Misused when essential to main content | [Aside](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/aside) |
| `<footer>` | Footer for document or section | Should not be used only for visual layout | [Footer](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/footer) |
| `<address>` | Contact information for nearest section | Misused for physical address of random locations | [Address](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/address) |
| `<figure>` | Self-contained referenced content | Misused as generic image wrapper without reference intent | [Figure](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/figure) |
| `<figcaption>` | Caption for `<figure>` | Must be first or last child of `<figure>` | [Figcaption](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/figcaption) |
| `<details>` | Disclosure widget for optional info | Misused for critical content | [Details](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/details) |
| `<summary>` | Summary or label for `<details>` | Should be concise and relevant | [Summary](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/summary) |
| `<time>` | Machine-readable date/time | Misused when not specifying valid date/time format | [Time](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/time) |
| `<mark>` | Highlights relevant text | Misused for visual highlight only without context | [Mark](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/mark) |
| `<blockquote>` | Quoted block content from external source | Misused without citing source or for small quotes | [Blockquote](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/blockquote) |
| `<cite>` | Cited source title | Misused for people's names (only for works, titles) | [Cite](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/cite) |
| `<abbr>` | Abbreviation/acronym | Misused without `title` attribute for full term | [Abbr](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/abbr) |
| `<code>` | Inline code | Misused as visual monospace text without code meaning | [Code](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/code) |
| `<kbd>` | User input (e.g., keyboard input) | Misused for non-input content | [Kbd](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/kbd) |
| `<samp>` | Program output | Rarely used; misused for input examples | [Samp](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/samp) |
| `<em>` | Stress emphasis | Misused only for italics without contextual stress | [Em](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/em) |
| `<strong>` | Important text | Misused solely for bold styling without conveying importance | [Strong](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/strong) |
| `<del>` | Deleted content | Misused for visual strikethrough without meaning | [Del](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/del) |
| `<ins>` | Inserted content | Misused without edit-tracking context | [Ins](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ins) |

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
