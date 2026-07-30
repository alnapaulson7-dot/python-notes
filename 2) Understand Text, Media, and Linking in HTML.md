# 📝 Text, Media & Linking in HTML

> HTML provides various elements to **format text**, **organize content**, **display images**, and **connect webpages**. These features make web pages more readable, interactive, and user-friendly.

---

# 📚 Contents

- Text Formatting Tags
- HTML Lists
- Images & Image Paths
- Hyperlinks & Navigation

---

# ✍️ Text Formatting Tags

Text formatting tags help emphasize, organize, and improve the readability of content.

---

## 🔹 `<b>` - Bold Text

Displays text in **bold** without adding any semantic meaning.

```html
<p><b>Welcome to HTML</b></p>
```

**Output:**

**Welcome to HTML**

> 📌 Used only for visual styling.

---

## 🔹 `<strong>` - Important Text

Displays bold text **and** tells browsers and screen readers that the text is important.

```html
<p><strong>Warning!</strong> Save your work before exiting.</p>
```

**Output:**

**Warning!** Save your work before exiting.

> ✅ Preferred over `<b>` when the text has importance.

---

## 🔹 `<i>` - Italic Text

Displays text in *italic* without adding meaning.

```html
<p><i>Learning HTML is fun.</i></p>
```

---

## 🔹 `<em>` - Emphasized Text

Displays italic text while giving semantic emphasis.

```html
<p>Please <em>read carefully</em> before submitting.</p>
```

> ✅ Preferred over `<i>` for emphasized content.

---

## 🔹 `<u>` - Underlined Text

Underlines text.

```html
<p><u>Important Note</u></p>
```

> ⚠️ Avoid overusing `<u>` because users may mistake it for hyperlinks.

---

## 📊 `<b>` vs `<strong>`

| `<b>` | `<strong>` |
|--------|------------|
| Visual formatting only | Indicates important content |
| No semantic meaning | Semantic tag |
| Less preferred | Recommended |

---

## 📊 `<i>` vs `<em>`

| `<i>` | `<em>` |
|--------|---------|
| Visual formatting | Emphasized content |
| No semantic meaning | Semantic tag |
| Mainly for styling | Better for accessibility & SEO |

---

# 📋 HTML Lists

Lists organize related items in a structured format.

HTML provides **three types of lists**.

---

# 1️⃣ Ordered List (`<ol>`)

Displays items with numbers.

```html
<ol>
    <li>HTML</li>
    <li>CSS</li>
    <li>JavaScript</li>
</ol>
```

### Output

1. HTML
2. CSS
3. JavaScript

### Common Uses

- Instructions
- Recipes
- Rankings
- Step-by-step guides

---

# 2️⃣ Unordered List (`<ul>`)

Displays items with bullet points.

```html
<ul>
    <li>Apple</li>
    <li>Mango</li>
    <li>Orange</li>
</ul>
```

### Output

- Apple
- Mango
- Orange

### Common Uses

- Navigation menus
- Feature lists
- Categories

---

# 3️⃣ Description List (`<dl>`)

Used to display **terms and their descriptions**.

### Tags Used

| Tag | Purpose |
|------|---------|
| `<dl>` | Description List |
| `<dt>` | Description Term |
| `<dd>` | Description Definition |

Example

```html
<dl>

    <dt>HTML</dt>

    <dd>Structure of a webpage.</dd>

    <dt>CSS</dt>

    <dd>Styles a webpage.</dd>

</dl>
```

---

## 📊 Comparison of Lists

| Ordered List | Unordered List | Description List |
|---------------|----------------|------------------|
| `<ol>` | `<ul>` | `<dl>` |
| Numbered | Bulleted | Term & Description |
| Steps | Categories | Definitions |

---

# 🖼️ Images in HTML

Images make webpages more attractive and informative.

Images are displayed using the `<img>` tag.

```html
<img src="images/logo.png" alt="Website Logo">
```

> 💡 The `<img>` tag is a **void element**, meaning it **does not require a closing tag**.

---

## Common Image Attributes

| Attribute | Purpose |
|-----------|---------|
| `src` | Specifies image location |
| `alt` | Alternative text if image cannot load |
| `width` | Image width |
| `height` | Image height |
| `title` | Tooltip shown on hover |

Example

```html
<img
    src="images/html.png"
    alt="HTML Logo"
    width="200"
    title="HTML Logo">
```

---

# 📂 Image Paths

Images can be loaded using **Relative Paths** or **Absolute Paths**.

---

## 📁 Relative Path

A relative path points to a file **inside your project folder**.

### Project Structure

```
MyProject/
│
├── index.html
│
└── images/
    └── logo.png
```

Example

```html
<img src="images/logo.png" alt="Logo">
```

### Advantages

- Faster
- Works offline
- Easy to move the project
- Best practice for websites

---

## 🌍 Absolute Path

An absolute path uses the complete URL of an image.

```html
<img
src="https://example.com/images/logo.png"
alt="Logo">
```

### Advantages

- Loads images hosted on another server
- No need to store images locally

### Disadvantages

- Requires internet
- Image may disappear if the external website removes it

---

## 📊 Relative vs Absolute Path

| Relative Path | Absolute Path |
|---------------|---------------|
| Local project | External website |
| Short path | Full URL |
| Faster | Depends on internet |
| Recommended | Use only when necessary |

---

# 🔗 Hyperlinks

Hyperlinks connect one webpage to another.

Created using the `<a>` (Anchor) tag.

```html
<a href="URL">Link Text</a>
```

---

## External Link

Links to another website.

```html
<a href="https://google.com">
    Visit Google
</a>
```

---

## Internal Link

Links to another page within the same website.

### Folder Structure

```
Website/
│
├── index.html
├── about.html
└── contact.html
```

Example

```html
<a href="about.html">
    About Us
</a>
```

---

## Open Link in New Tab

```html
<a
href="https://google.com"
target="_blank">

Google

</a>
```

### Common Attributes

| Attribute | Purpose |
|-----------|---------|
| `href` | Destination URL |
| `target="_blank"` | Opens link in a new tab |
| `title` | Tooltip on hover |

---

# 🧭 Website Navigation

Navigation allows users to move between different pages of a website.

Example folder structure:

```
Portfolio/
│
├── index.html
├── about.html
├── projects.html
├── services.html
└── contact.html
```

Navigation Menu

```html
<nav>

    <a href="index.html">Home</a>

    <a href="about.html">About</a>

    <a href="projects.html">Projects</a>

    <a href="services.html">Services</a>

    <a href="contact.html">Contact</a>

</nav>
```

> 💡 The `<nav>` tag is a **semantic element** used to group navigation links.

---

# 💻 Complete Example

```html
<!DOCTYPE html>
<html>

<head>
    <title>Text, Media & Links</title>
</head>

<body>

<h1>Learning HTML</h1>

<p>
    <strong>HTML</strong> is the
    <em>foundation</em> of web development.
</p>

<p>
    <u>Today's Topics</u>
</p>

<ul>
    <li>Text Formatting</li>
    <li>Lists</li>
    <li>Images</li>
    <li>Hyperlinks</li>
</ul>

<img
src="images/html.png"
alt="HTML Logo"
width="180">

<br><br>

<nav>

<a href="about.html">About</a> |

<a href="contact.html">Contact</a> |

<a href="https://developer.mozilla.org" target="_blank">
MDN Docs
</a>

</nav>

</body>
</html>
```

---

# 💎 Best Practices

✅ Use `<strong>` instead of `<b>` for important text.

✅ Use `<em>` instead of `<i>` when emphasizing content.

✅ Always provide meaningful `alt` text for images.

✅ Organize images inside a dedicated `images/` folder.

✅ Prefer **relative paths** for images within your project.

✅ Use semantic `<nav>` for navigation menus.

✅ Open external websites in a new tab only when it improves the user experience.

---

# ⚠️ Common Mistakes

❌ Forgetting the `alt` attribute.

❌ Using absolute paths for local images.

❌ Using `<br>` repeatedly instead of proper HTML structure.

❌ Forgetting to close list tags (`</li>`).

❌ Mixing ordered and unordered lists incorrectly.

❌ Using `<b>` everywhere instead of `<strong>`.

---

# ⚡ Quick Revision

| Element | Purpose |
|----------|---------|
| `<b>` | Bold text (visual) |
| `<strong>` | Important text |
| `<i>` | Italic text (visual) |
| `<em>` | Emphasized text |
| `<u>` | Underlined text |
| `<ol>` | Ordered list |
| `<ul>` | Unordered list |
| `<dl>` | Description list |
| `<li>` | List item |
| `<img>` | Displays an image |
| `src` | Image source |
| `alt` | Alternative text |
| `width` | Image width |
| `height` | Image height |
| `<a>` | Hyperlink |
| `href` | Link destination |
| `target="_blank"` | Opens link in a new tab |
| `<nav>` | Navigation section |

---

# 🚀 Key Takeaway

HTML provides powerful elements to **format text**, **organize information using lists**, **display images**, and **connect web pages through hyperlinks**. Using semantic tags like `<strong>`, `<em>`, and `<nav>`, along with meaningful image paths and accessible attributes such as `alt`, helps create websites that are easier to maintain, more user-friendly, and optimized for search engines and assistive technologies.
````
