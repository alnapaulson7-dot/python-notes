# 🎨 CSS Basics

> **CSS (Cascading Style Sheets)** is a stylesheet language used to **control the appearance and layout of HTML elements**. While HTML creates the structure of a webpage, CSS makes it visually attractive by adding colors, fonts, spacing, animations, and layouts.

---

# 📚 Contents

- What is CSS?
- How CSS Works with HTML
- Ways to Apply CSS
- CSS Syntax
- CSS Selectors
- Complete Example

---

# 🎯 What is CSS?

Imagine building a house:

- 🧱 **HTML** → Structure (Walls, Doors, Windows)
- 🎨 **CSS** → Design (Paint, Furniture, Decoration)
- ⚡ **JavaScript** → Functionality (Lights, Fans, Smart Devices)

Without CSS, every webpage looks plain and unstyled.

---

## Without CSS

```html
<h1>Welcome</h1>

<p>This is my website.</p>

<button>Click Me</button>
```

Output:

```
Welcome

This is my website.

[ Click Me ]
```

---

## With CSS

```css
h1{
    color: blue;
}

button{
    background-color: green;
    color: white;
}
```

Output:

- 🔵 Blue Heading
- 🟢 Green Button
- ⚪ White Button Text

CSS makes websites look professional and user-friendly.

---

# 🔄 How CSS Works with HTML

CSS selects HTML elements and applies styles to them.

### HTML

```html
<h1>Hello World</h1>
```

### CSS

```css
h1{
    color: blue;
}
```

### Result

The `<h1>` text appears **blue**.

---

## Flow of CSS

```
HTML Element
      │
      ▼
CSS Selector
      │
      ▼
CSS Properties
      │
      ▼
Styled Webpage
```

---

# 🛠️ Ways to Apply CSS

There are **three ways** to add CSS to HTML.

---

# 1️⃣ Inline CSS

CSS is written directly inside an HTML element using the `style` attribute.

### Syntax

```html
<h1 style="color: blue;">Hello World</h1>
```

### Advantages

- Quick styling
- Good for testing

### Disadvantages

- Difficult to maintain
- Repeats code
- Not recommended for large projects

---

# 2️⃣ Internal CSS

CSS is written inside the `<style>` tag within the `<head>` section.

```html
<head>

<style>

h1{
    color: blue;
}

</style>

</head>
```

### Advantages

- Styles one webpage
- Better than inline CSS

### Disadvantages

- Cannot be shared across multiple pages

---

# 3️⃣ External CSS ⭐ (Recommended)

CSS is written in a separate `.css` file and linked to the HTML document.

### HTML

```html
<head>

<link rel="stylesheet" href="style.css">

</head>
```

### style.css

```css
h1{
    color: blue;
}
```

### Advantages

✅ Reusable

✅ Easy to maintain

✅ Faster loading using browser caching

✅ Used in real-world projects

---

## 📊 Comparison

| Method | Location | Best For |
|----------|----------|----------|
| Inline | Inside HTML tag | Small changes |
| Internal | `<style>` tag | Single webpage |
| External | Separate `.css` file | Real projects ⭐ |

---

# 🧩 CSS Syntax

Every CSS rule has **three parts**.

```css
selector{
    property: value;
}
```

---

## Example

```css
h1{

    color: blue;

}
```

### Breakdown

| Part | Example | Purpose |
|------|---------|---------|
| Selector | `h1` | Selects an HTML element |
| Property | `color` | Defines what to change |
| Value | `blue` | Specifies the new style |

---

## Multiple Properties

```css
h1{

    color: blue;

    font-size: 40px;

    text-align: center;

}
```

Each property ends with a semicolon (`;`).

---

# 🎯 CSS Selectors

Selectors tell CSS **which HTML elements to style**.

---

# 1️⃣ Element Selector

Selects all elements of a particular type.

### HTML

```html
<p>Hello</p>

<p>Welcome</p>
```

### CSS

```css
p{

    color: blue;

}
```

All `<p>` elements become blue.

---

# 2️⃣ Class Selector

A class can be used on **multiple elements**.

### HTML

```html
<p class="highlight">Hello</p>

<h2 class="highlight">Welcome</h2>
```

### CSS

```css
.highlight{

    color: red;

}
```

Both elements become red.

> 💡 A class starts with a **dot (`.`)** in CSS.

---

# 3️⃣ ID Selector

An ID should be **unique** on a webpage.

### HTML

```html
<h1 id="title">

Welcome

</h1>
```

### CSS

```css
#title{

    color: green;

}
```

> 💡 An ID starts with a **hash (`#`)** in CSS.

---

# 4️⃣ Group Selector

Styles multiple elements using one rule.

### HTML

```html
<h1>Hello</h1>

<p>Welcome</p>
```

### CSS

```css
h1,
p{

    color: blue;

}
```

Both `<h1>` and `<p>` become blue.

---

## 📊 Selector Summary

| Selector | Symbol | Example |
|-----------|--------|---------|
| Element | None | `p` |
| Class | `.` | `.box` |
| ID | `#` | `#header` |
| Group | `,` | `h1, p` |

---

# 💻 Complete Example

## HTML

```html
<!DOCTYPE html>
<html>

<head>

<link rel="stylesheet" href="style.css">

</head>

<body>

<h1 id="title">Welcome</h1>

<p class="text">
Learning CSS is fun.
</p>

<p class="text">
CSS makes websites beautiful.
</p>

<button>Click Me</button>

</body>

</html>
```

---

## CSS

```css
#title{

    color: navy;

    text-align: center;

}

.text{

    color: gray;

    font-size: 18px;

}

button{

    background-color: green;

    color: white;

    padding: 10px 20px;

}
```

---

# 💎 Best Practices

✅ Use **External CSS** for real projects.

✅ Use **class selectors** for reusable styles.

✅ Use **ID selectors** only for unique elements.

✅ Keep CSS code properly indented.

✅ Give meaningful class and ID names.

✅ Group similar styles to reduce repetition.

---

# ⚠️ Common Mistakes

❌ Forgetting to link the external CSS file.

❌ Missing semicolons after properties.

❌ Using spaces in class or ID names.

❌ Using the same ID for multiple elements.

❌ Writing CSS inside `<body>` instead of `<head>` (for internal CSS).

❌ Confusing `.` (class) with `#` (ID).

---

# ⚡ Quick Revision

| Concept | Remember |
|----------|----------|
| CSS | Styles HTML webpages |
| Inline CSS | `style=""` attribute |
| Internal CSS | `<style>` tag |
| External CSS | Separate `.css` file |
| Selector | Chooses an element |
| Property | What to style |
| Value | Style applied |
| Element Selector | `p` |
| Class Selector | `.className` |
| ID Selector | `#idName` |
| Group Selector | `h1, p` |

---

# 🚀 Key Takeaway

CSS transforms plain HTML into visually appealing webpages by applying styles such as colors, fonts, spacing, and layouts. It works by selecting HTML elements and assigning style rules using **selectors, properties, and values**. While CSS can be added using **inline**, **internal**, or **external** methods, **external CSS** is the preferred approach for professional web development because it keeps code organized, reusable, and easy to maintain.
````
