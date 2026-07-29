````markdown
# 📝 Text, Media & Linking in HTML

> Learn how to format text, display images, create lists, and connect web pages using hyperlinks.

---

# 📚 Contents

- Text Formatting Tags
- Lists
- Images & Image Paths
- Hyperlinks & Navigation

---

# ✍️ Text Formatting Tags

HTML provides different tags to format text and give it meaning.

| Tag | Description | Example |
|------|-------------|---------|
| `<b>` | Makes text **bold** (visual only) | `<b>Hello</b>` |
| `<strong>` | Indicates **important text** (semantic) | `<strong>Warning!</strong>` |
| `<i>` | Makes text *italic* (visual only) | `<i>Hello</i>` |
| `<em>` | Adds *emphasis* (semantic) | `<em>Important</em>` |
| `<u>` | Underlines text | `<u>HTML</u>` |

### Example

```html
<p>
    <b>Bold</b><br>
    <strong>Strong</strong><br>
    <i>Italic</i><br>
    <em>Emphasized</em><br>
    <u>Underline</u>
</p>
```

> 💡 **Tip:** Prefer `<strong>` over `<b>` and `<em>` over `<i>` because they provide meaning, improving accessibility and SEO.

---

# 📋 Lists

Lists help organize content.

## 🔹 Ordered List (`<ol>`)

Displays items with numbers.

```html
<ol>
    <li>HTML</li>
    <li>CSS</li>
    <li>JavaScript</li>
</ol>
```

**Output**

1. HTML
2. CSS
3. JavaScript

---

## 🔹 Unordered List (`<ul>`)

Displays items with bullets.

```html
<ul>
    <li>Apple</li>
    <li>Mango</li>
    <li>Orange</li>
</ul>
```

**Output**

- Apple
- Mango
- Orange

---

## 🔹 Description List (`<dl>`)

Used for terms and their descriptions.

- `<dl>` → Description List
- `<dt>` → Description Term
- `<dd>` → Description Definition

```html
<dl>
    <dt>HTML</dt>
    <dd>Structure of a webpage.</dd>

    <dt>CSS</dt>
    <dd>Styles a webpage.</dd>
</dl>
```

---

# 🖼️ Images

Images are added using the `<img>` tag.

## Syntax

```html
<img src="image.jpg" alt="Description">
```

### Common Attributes

| Attribute | Purpose |
|-----------|---------|
| `src` | Specifies image location |
| `alt` | Alternative text if image fails to load |
| `width` | Sets image width |
| `height` | Sets image height |
| `title` | Displays a tooltip on hover |

### Example

```html
<img
    src="images/html.png"
    alt="HTML Logo"
    width="200"
    title="HTML Logo">
```

---

# 📂 Image Paths

## ✅ Relative Path

Points to a file inside your project.

```
Project/
│
├── index.html
└── images/
    └── logo.png
```

```html
<img src="images/logo.png" alt="Logo">
```

✔️ Best for local project files.

---

## 🌍 Absolute Path

Uses the complete web address.

```html
<img src="https://example.com/logo.png" alt="Logo">
```

✔️ Used for images hosted online.

---

## 📊 Relative vs Absolute Path

| Relative Path | Absolute Path |
|---------------|---------------|
| Inside your project | External website |
| Short path | Full URL |
| Faster for local projects | Requires internet |
| Easy to move project | Depends on external server |

---

# 🔗 Hyperlinks

Hyperlinks connect one webpage to another.

## Syntax

```html
<a href="URL">Link Text</a>
```

### External Link

```html
<a href="https://google.com">
    Visit Google
</a>
```

---

### Internal Link

Suppose your project looks like this:

```
Website/
│
├── index.html
└── about.html
```

Navigate to another page:

```html
<a href="about.html">
    About Us
</a>
```

---

### Open Link in a New Tab

```html
<a href="https://google.com" target="_blank">
    Google
</a>
```

| Attribute | Purpose |
|-----------|---------|
| `href` | Destination URL |
| `target="_blank"` | Opens link in a new tab |

---

# 🧭 Navigation Example

```
Website/
│
├── index.html
├── about.html
├── services.html
└── contact.html
```

```html
<nav>
    <a href="index.html">Home</a> |
    <a href="about.html">About</a> |
    <a href="services.html">Services</a> |
    <a href="contact.html">Contact</a>
</nav>
```

This creates a simple navigation menu between pages.

---

# 💡 Quick Comparison

## `<b>` vs `<strong>`

| `<b>` | `<strong>` |
|--------|------------|
| Visual bold only | Indicates important text |
| No semantic meaning | Semantic tag |
| Less preferred | Recommended |

---

## `<i>` vs `<em>`

| `<i>` | `<em>` |
|--------|---------|
| Visual italic only | Adds emphasis |
| No semantic meaning | Semantic tag |
| Less preferred | Recommended |

---

# 🎯 Complete Example

```html
<!DOCTYPE html>
<html>

<head>
    <title>HTML Example</title>
</head>

<body>

<h1>Welcome to My Website</h1>

<p>
    <strong>HTML</strong> is the
    <em>foundation</em> of web development.
</p>

<img
    src="images/html.png"
    alt="HTML Logo"
    width="180">

<h2>Technologies</h2>

<ul>
    <li>HTML</li>
    <li>CSS</li>
    <li>JavaScript</li>
</ul>

<nav>
    <a href="about.html">About</a> |
    <a href="contact.html">Contact</a>
</nav>

</body>
</html>
```

---

# ⚡ Quick Revision

✅ `<b>` → Bold (visual)

✅ `<strong>` → Important text

✅ `<i>` → Italic (visual)

✅ `<em>` → Emphasized text

✅ `<u>` → Underlined text

✅ `<ol>` → Ordered list

✅ `<ul>` → Unordered list

✅ `<dl>` → Description list

✅ `<img>` → Displays an image

✅ `src` → Image source

✅ `alt` → Alternative text

✅ Relative Path → Inside your project

✅ Absolute Path → Full web URL

✅ `<a>` → Creates hyperlinks

✅ `href` → Link destination

✅ `target="_blank"` → Opens link in a new tab

---

> 🚀 **Key Takeaway:** HTML uses formatting tags to style text, lists to organize information, images to display media, and hyperlinks to connect webpages, making websites informative and easy to navigate.
````
