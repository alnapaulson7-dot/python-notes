# 🌐 HTML Basics

> HTML (**HyperText Markup Language**) is the standard markup language used to create the **structure of a web page**.

---

# 📑 Contents

- HTML Document Structure
- Common HTML Elements
- HTML Attributes
- Semantic vs Non-Semantic Tags

---

# 🏗️ HTML Document Structure

Every HTML page follows this basic structure:

```html
<!DOCTYPE html>
<html>
<head>
    <title>My Website</title>
</head>

<body>
    <h1>Hello World!</h1>
    <p>Welcome to HTML.</p>
</body>
</html>
```

## 📌 Explanation

| Tag | Purpose |
|------|---------|
| `<!DOCTYPE html>` | Declares the document as HTML5 |
| `<html>` | Root element that contains the entire webpage |
| `<head>` | Stores metadata like title, CSS, and JavaScript links |
| `<body>` | Contains everything visible on the webpage |

> 💡 **Remember:** Only the content inside `<body>` is displayed in the browser.

---

# 🧩 Common HTML Elements

## 🔹 Headings

Used for titles and section headings.

```html
<h1>Main Heading</h1>
<h2>Sub Heading</h2>
<h3>Heading 3</h3>
```

📌 HTML provides **6 heading levels (`h1` → `h6`)**.

---

## 🔹 Paragraph

Used for normal text.

```html
<p>This is a paragraph.</p>
```

---

## 🔹 Hyperlink

Creates a clickable link.

```html
<a href="https://google.com">Visit Google</a>
```

---

## 🔹 Image

Displays an image.

```html
<img src="cat.jpg" alt="Cute Cat">
```

---

# 🏷️ HTML Attributes

Attributes provide **extra information** about HTML elements.

### Syntax

```html
<tag attribute="value">
```

## `href`

Specifies the destination of a hyperlink.

```html
<a href="https://google.com">Google</a>
```

---

## `src`

Specifies the image location.

```html
<img src="image.png">
```

---

## `alt`

Alternative text displayed if the image cannot load.

```html
<img src="cat.jpg" alt="Cute Cat">
```

✅ Improves accessibility.

---

## `title`

Displays a tooltip when the mouse hovers over an element.

```html
<p title="Hello!">Hover over me</p>
```

---

## 📋 Attribute Summary

| Attribute | Used With | Purpose |
|-----------|-----------|---------|
| `href` | `<a>` | Link destination |
| `src` | `<img>` | Image source |
| `alt` | `<img>` | Alternative text |
| `title` | Most elements | Tooltip text |

---

# 🧠 Semantic vs Non-Semantic Tags

## ✅ Semantic Tags

Semantic tags clearly describe the purpose of their content.

```html
<header>
<nav>
<main>
<section>
<article>
<footer>
```

### Why use them?

- Better readability
- Better SEO
- Better accessibility
- Easier maintenance

---

## ❌ Non-Semantic Tags

These tags do **not** describe the content.

```html
<div>
<span>
```

They are mainly used for layout and styling.

---

## ⚖️ Comparison

| Semantic | Non-Semantic |
|-----------|--------------|
| `<header>` | `<div>` |
| `<nav>` | `<div>` |
| `<main>` | `<div>` |
| `<section>` | `<div>` |
| `<article>` | `<div>` |
| `<footer>` | `<div>` |

---

# 🎯 Example

```html
<body>

<header>
    <h1>My Portfolio</h1>
</header>

<nav>
    <a href="#">Home</a>
    <a href="#">About</a>
</nav>

<main>

<section>
    <h2>About Me</h2>
    <p>I am learning HTML.</p>
</section>

</main>

<footer>
    © 2026
</footer>

</body>
```

---

# 📝 Quick Revision

- 📌 HTML = Structure of a webpage
- 📌 `<head>` = Metadata
- 📌 `<body>` = Visible content
- 📌 `href` = Link
- 📌 `src` = Image source
- 📌 `alt` = Alternative text
- 📌 `title` = Tooltip
- 📌 Semantic tags describe meaning
- 📌 Non-semantic tags do not describe meaning

---

## 🚀 Key Takeaway

> **HTML provides the structure of a webpage, attributes add extra information, and semantic tags make webpages more meaningful, accessible, and easier to maintain.**
