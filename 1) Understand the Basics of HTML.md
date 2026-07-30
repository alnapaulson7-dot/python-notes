# 🌐 HTML Basics

> **HTML (HyperText Markup Language)** is the standard markup language used to create the **structure and content of web pages**. It tells the browser **what** to display, while CSS controls **how** it looks and JavaScript controls **how** it behaves.

---

# 📚 Contents

- HTML Document Structure
- Common HTML Elements
- HTML Attributes
- Semantic vs Non-Semantic Tags

---

# 🏗️ HTML Document Structure

Every HTML page follows a standard structure.

```html
<!DOCTYPE html>
<html>
<head>
    <title>My First Webpage</title>
</head>

<body>
    <h1>Hello World!</h1>
    <p>Welcome to HTML.</p>
</body>
</html>
```

---

## 📌 Understanding Each Tag

### 1️⃣ `<!DOCTYPE html>`

```html
<!DOCTYPE html>
```

### Purpose

Declares that the document uses **HTML5**.

### Why is it Important?

Without it, browsers may enter **Quirks Mode**, causing inconsistent rendering across browsers.

> 💡 Always keep this as the **first line** of every HTML document.

---

### 2️⃣ `<html>`

```html
<html>
```

### Purpose

The **root element** of every HTML page.

Everything inside the webpage is enclosed within this tag.

```html
<html>

    ...

</html>
```

---

### 3️⃣ `<head>`

The `<head>` contains information **about the webpage**, not content visible to users.

Common elements inside `<head>` include:

- `<title>`
- `<meta>`
- `<link>`
- `<style>`
- `<script>`

Example

```html
<head>

    <title>My Website</title>

</head>
```

### Browser View

```
┌──────────────────────────┐
│ My Website               │ ← Browser Tab
└──────────────────────────┘
```

---

### 4️⃣ `<body>`

The `<body>` contains everything visible on the webpage.

Examples:

- Headings
- Paragraphs
- Images
- Videos
- Forms
- Tables
- Buttons
- Lists

Example

```html
<body>

    <h1>Welcome</h1>

    <p>This is my website.</p>

</body>
```

---

## 📊 HTML Document Hierarchy

```text
HTML Document
│
├── <!DOCTYPE html>
│
└── <html>
      │
      ├── <head>
      │      ├── title
      │      ├── meta
      │      ├── link
      │      └── script
      │
      └── <body>
             ├── headings
             ├── paragraphs
             ├── images
             ├── tables
             ├── forms
             └── links
```

---

# 🧩 Common HTML Elements

HTML elements are building blocks used to display different types of content.

---

## 🔹 Headings

Headings define titles and section headings.

```html
<h1>Main Heading</h1>

<h2>Sub Heading</h2>

<h3>Heading 3</h3>

<h4>Heading 4</h4>

<h5>Heading 5</h5>

<h6>Heading 6</h6>
```

### Notes

- `<h1>` → Most important heading.
- `<h6>` → Least important heading.
- Normally, a webpage should have **one main `<h1>`** representing the page topic.

---

## 🔹 Paragraph

Paragraphs display blocks of text.

```html
<p>This is a paragraph.</p>
```

Example

```html
<p>HTML is easy to learn and forms the foundation of web development.</p>
```

---

## 🔹 Hyperlinks

The `<a>` tag creates clickable links.

```html
<a href="https://google.com">
    Visit Google
</a>
```

### Uses

- Navigate to another webpage
- Download files
- Jump to another section
- Open email links

---

## 🔹 Images

The `<img>` tag displays images.

```html
<img src="cat.jpg" alt="Cute Cat">
```

Unlike most tags,

```html
<img>
```

is a **void element**, meaning it **does not require a closing tag**.

---

# 🏷️ HTML Attributes

Attributes provide **additional information** about HTML elements.

## Syntax

```html
<tag attribute="value">
```

Example

```html
<a href="https://google.com">
```

Here,

- `href` → Attribute
- `"https://google.com"` → Value

---

## 🔹 href

Specifies the destination of a hyperlink.

```html
<a href="https://youtube.com">
    YouTube
</a>
```

Used only with:

```html
<a>
```

---

## 🔹 src

Specifies the location of an image or other external resource.

```html
<img src="images/logo.png">
```

`src` stands for **Source**.

---

## 🔹 alt

Alternative text displayed when an image cannot be loaded.

```html
<img
    src="cat.jpg"
    alt="Cute Cat">
```

### Why is `alt` Important?

- Improves accessibility.
- Helps visually impaired users using screen readers.
- Displays text if the image is missing.
- Improves SEO.

---

## 🔹 title

Displays a tooltip when the mouse hovers over an element.

```html
<p title="This is HTML">
    Hover over me
</p>
```

---

## 📊 Attribute Summary

| Attribute | Used With | Purpose |
|-----------|-----------|---------|
| `href` | `<a>` | Destination of hyperlink |
| `src` | `<img>` | Image location |
| `alt` | `<img>` | Alternative image description |
| `title` | Most HTML elements | Tooltip on hover |

---

# 🧠 Semantic vs Non-Semantic Tags

One of the biggest improvements introduced in HTML5 was **semantic elements**.

---

## ✅ Semantic Tags

Semantic tags clearly describe the purpose of the content they contain.

Examples

```html
<header>

<nav>

<main>

<section>

<article>

<aside>

<footer>
```

### Why Use Semantic Tags?

- Improves code readability.
- Makes maintenance easier.
- Improves Search Engine Optimization (SEO).
- Better accessibility for screen readers.
- Helps browsers understand page structure.

Example

```html
<header>

    <h1>My Portfolio</h1>

</header>
```

Even without reading the content, developers know this is the page header.

---

## ❌ Non-Semantic Tags

Non-semantic tags do not describe the meaning of their content.

Examples

```html
<div>

<span>
```

These are mainly used for:

- Layout
- Styling
- Grouping elements

Example

```html
<div>

Navigation Menu

</div>
```

Looking at this code alone, we cannot tell whether it's a navigation bar, footer, or sidebar.

---

## 📊 Semantic vs Non-Semantic

| Semantic Tags | Non-Semantic Tags |
|---------------|-------------------|
| Describe meaning | Describe nothing |
| Better SEO | Poor SEO |
| Better accessibility | Limited accessibility |
| Easier to understand | Depends on developer comments |
| Example: `<header>` | Example: `<div>` |

---

## 💻 Practical Example

```html
<body>

<header>

    <h1>My Website</h1>

</header>

<nav>

    <a href="#">Home</a>

    <a href="#">About</a>

</nav>

<main>

<section>

    <h2>About HTML</h2>

    <p>HTML provides the structure of webpages.</p>

    <img
        src="html.png"
        alt="HTML Logo">

</section>

</main>

<footer>

    <p>© 2026 My Website</p>

</footer>

</body>
```

---

# 💡 Best Practices

✅ Use semantic HTML whenever possible.

✅ Always include the `alt` attribute for images.

✅ Use only one `<h1>` per page.

✅ Keep HTML properly indented for readability.

✅ Use meaningful file and folder names.

✅ Write tags and attribute names in lowercase.

---

# ⚠️ Common Mistakes

❌ Forgetting `<!DOCTYPE html>`

❌ Using `<br>` repeatedly for spacing instead of CSS

❌ Missing the `alt` attribute on images

❌ Using too many `<div>` elements instead of semantic tags

❌ Skipping heading levels unnecessarily (e.g., `<h1>` directly to `<h4>`)

---

# ⚡ Quick Revision

| Concept | Remember |
|----------|----------|
| HTML | Structure of a webpage |
| `<!DOCTYPE html>` | Declares HTML5 |
| `<html>` | Root element |
| `<head>` | Metadata (not visible) |
| `<body>` | Visible webpage content |
| `<h1> - <h6>` | Headings |
| `<p>` | Paragraph |
| `<a>` | Hyperlink |
| `<img>` | Displays image |
| `href` | Link destination |
| `src` | Image source |
| `alt` | Alternative text |
| `title` | Tooltip |
| Semantic Tags | Describe content meaning |
| Non-Semantic Tags | Used mainly for layout |

---

# 🚀 Key Takeaway

HTML is the **foundation of every website**. It provides the structure of a webpage using elements like headings, paragraphs, images, and links. Attributes such as `href`, `src`, `alt`, and `title` add additional information to elements. Using **semantic HTML** makes webpages more accessible, SEO-friendly, and easier to maintain, while non-semantic tags like `<div>` and `<span>` are primarily used for layout and styling.
