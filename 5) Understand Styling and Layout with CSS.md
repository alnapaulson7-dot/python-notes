# 🎨 Styling & Layout with CSS

> CSS not only makes a webpage look attractive but also controls **how elements are arranged and positioned**. Understanding styling and layout is one of the most important skills in web development.

---

# 📚 Contents

- Colors
- Fonts & Text Styling
- CSS Box Model
- Display Properties
- Positioning
- Complete Example

---

# 🎨 Colors in CSS

Colors make webpages attractive and improve readability.

There are multiple ways to specify colors.

---

## 1️⃣ Color Name

```css
h1{
    color: blue;
}
```

---

## 2️⃣ HEX Color

HEX values start with `#`.

```css
h1{
    color: #3498db;
}
```

Example

| Color | HEX |
|--------|------|
| White | `#FFFFFF` |
| Black | `#000000` |
| Red | `#FF0000` |
| Blue | `#0000FF` |

---

## 3️⃣ RGB

RGB stands for **Red, Green, Blue**.

```css
p{
    color: rgb(255,0,0);
}
```

---

## 4️⃣ RGBA

RGBA adds an **Alpha (Transparency)** value.

```css
background-color: rgba(0,0,255,0.5);
```

`0` = Fully Transparent

`1` = Fully Visible

---

## Background Color

```css
body{
    background-color: lightgray;
}
```

---

## 📊 Common Color Properties

| Property | Purpose |
|----------|---------|
| `color` | Text color |
| `background-color` | Background color |

---

# 🔤 Fonts & Text Styling

CSS allows you to customize the appearance of text.

---

## Font Family

Changes the font.

```css
p{
    font-family: Arial;
}
```

Example

```css
font-family: Arial, sans-serif;
```

> 💡 If the first font isn't available, the browser uses the next one.

---

## Font Size

```css
font-size: 20px;
```

---

## Font Weight

```css
font-weight: bold;
```

Values

- normal
- bold
- 100–900

---

## Font Style

```css
font-style: italic;
```

---

## Text Alignment

```css
text-align: center;
```

Possible values

- left
- right
- center
- justify

---

## Text Decoration

```css
text-decoration: underline;
```

Common values

- underline
- none
- line-through
- overline

Removing underline from links

```css
a{
    text-decoration: none;
}
```

---

## Text Transform

Changes letter casing.

```css
text-transform: uppercase;
```

Other values

- lowercase
- capitalize

---

## Letter Spacing

```css
letter-spacing: 2px;
```

---

## Line Height

Controls spacing between lines.

```css
line-height: 1.8;
```

---

## 📊 Text Styling Summary

| Property | Purpose |
|----------|---------|
| `font-family` | Font style |
| `font-size` | Text size |
| `font-weight` | Boldness |
| `font-style` | Italic text |
| `text-align` | Align text |
| `text-decoration` | Underline, etc. |
| `text-transform` | Change letter case |
| `letter-spacing` | Space between letters |
| `line-height` | Space between lines |

---

# 📦 CSS Box Model

Every HTML element is treated as a **rectangular box**.

The Box Model determines how much space an element occupies.

```
+---------------------------+
|         Margin            |
|  +---------------------+  |
|  |      Border         |  |
|  | +-----------------+ |  |
|  | |    Padding      | |  |
|  | | +-------------+ | |  |
|  | | |   Content   | | |  |
|  | | +-------------+ | |  |
|  | +-----------------+ |  |
|  +---------------------+  |
+---------------------------+
```

---

## 1️⃣ Content

The actual text, image, or other content.

```css
width:300px;
height:150px;
```

---

## 2️⃣ Padding

Space **inside** the border.

```css
padding:20px;
```

Example

```
Border

  Padding

     Content

  Padding

Border
```

---

## 3️⃣ Border

Surrounds the padding and content.

```css
border:2px solid black;
```

Syntax

```css
border: width style color;
```

Example

```css
border:3px dashed red;
```

---

## 4️⃣ Margin

Space **outside** the border.

```css
margin:30px;
```

Used to separate elements.

---

## 📊 Box Model Summary

| Property | Purpose |
|----------|---------|
| Content | Actual element |
| Padding | Space inside border |
| Border | Surrounds content |
| Margin | Space outside border |

---

## Complete Example

```css
.box{

    width:250px;

    padding:20px;

    border:2px solid blue;

    margin:30px;

}
```

---

# 🧩 Display Properties

The `display` property controls **how elements appear on a webpage**.

---

## 1️⃣ Block

Starts on a new line and takes the full available width.

Examples

- `<div>`
- `<p>`
- `<h1>`

```css
display:block;
```

---

## 2️⃣ Inline

Takes only the required width.

Examples

- `<span>`
- `<a>`
- `<strong>`

```css
display:inline;
```

Inline elements ignore `width` and `height`.

---

## 3️⃣ Inline-Block

Behaves like inline but allows width and height.

```css
display:inline-block;
```

Used for

- Navigation Buttons
- Cards
- Menus

---

## 4️⃣ None

Completely hides an element.

```css
display:none;
```

The element is removed from the page layout.

---

## 📊 Display Comparison

| Display | New Line | Width/Height Allowed |
|----------|----------|----------------------|
| Block | ✅ Yes | ✅ Yes |
| Inline | ❌ No | ❌ No |
| Inline-block | ❌ No | ✅ Yes |
| None | Hidden | Not Visible |

---

# 📍 Positioning

The `position` property controls where an element appears.

---

## 1️⃣ Static (Default)

Every element is **static** unless changed.

```css
position:static;
```

Cannot use `top`, `left`, `right`, or `bottom`.

---

## 2️⃣ Relative

Moves relative to its original position.

```css
.box{

position:relative;

top:20px;

left:30px;

}
```

The original space is still reserved.

---

## 3️⃣ Absolute

Moves relative to the nearest positioned parent.

```css
.box{

position:absolute;

top:50px;

left:80px;

}
```

If no positioned parent exists, it is positioned relative to the webpage.

---

## 4️⃣ Fixed

Remains fixed even when the page scrolls.

```css
position:fixed;

bottom:20px;

right:20px;
```

Common Uses

- Chat Button
- Back to Top Button
- Floating Menu

---

## 5️⃣ Sticky

Acts like relative until a certain scroll position, then sticks to the screen.

```css
position:sticky;

top:0;
```

Common Uses

- Sticky Navigation Bar
- Sticky Table Header

---

## 📊 Position Comparison

| Position | Moves With Scroll | Uses Original Space |
|----------|-------------------|---------------------|
| Static | ✅ Yes | ✅ Yes |
| Relative | ✅ Yes | ✅ Yes |
| Absolute | ❌ No | ❌ No |
| Fixed | ❌ Stays Fixed | ❌ No |
| Sticky | Partially | ✅ Yes |

---

# 💻 Complete Example

## HTML

```html
<div class="card">

<h2>CSS Card</h2>

<p>Learning CSS Layout</p>

<button>Read More</button>

</div>
```

---

## CSS

```css
.card{

    width:300px;

    padding:20px;

    border:2px solid #333;

    margin:20px;

    background-color:#f5f5f5;

}

h2{

    color:navy;

    text-align:center;

}

button{

    background-color:green;

    color:white;

    border:none;

    padding:10px 20px;

    display:inline-block;

}
```

---

# 💎 Best Practices

✅ Use readable color combinations for accessibility.

✅ Always include a fallback font (e.g., `Arial, sans-serif`).

✅ Understand the Box Model before learning Flexbox or Grid.

✅ Use `margin` for spacing **between** elements.

✅ Use `padding` for spacing **inside** elements.

✅ Avoid using `position:absolute` unless necessary.

✅ Use `position:sticky` for navigation bars.

✅ Use `display:none` only when you want to completely hide an element.

---

# ⚠️ Common Mistakes

❌ Confusing `margin` and `padding`.

❌ Forgetting that inline elements ignore `width` and `height`.

❌ Using too many fixed-position elements.

❌ Applying `position:absolute` without a positioned parent.

❌ Choosing text and background colors with poor contrast.

❌ Overusing different fonts on the same page.

---

# ⚡ Quick Revision

| Concept | Remember |
|----------|----------|
| `color` | Text color |
| `background-color` | Background color |
| `font-family` | Font type |
| `font-size` | Text size |
| `font-weight` | Boldness |
| `text-align` | Text alignment |
| `text-decoration` | Underline or remove underline |
| Margin | Outside spacing |
| Border | Surrounds the element |
| Padding | Inside spacing |
| Content | Actual element content |
| `display:block` | Full width, new line |
| `display:inline` | Same line, no width/height |
| `display:inline-block` | Same line with width/height |
| `display:none` | Hides the element |
| `position:static` | Default position |
| `position:relative` | Moves from original position |
| `position:absolute` | Relative to nearest positioned parent |
| `position:fixed` | Fixed on the screen |
| `position:sticky` | Sticks while scrolling |

---

# 🚀 Key Takeaway

CSS styling controls the **visual appearance** of a webpage through colors, fonts, and text properties. The **Box Model** defines how elements occupy space using **content, padding, border, and margin**. **Display properties** determine how elements are rendered in the layout, while **positioning** provides precise control over where elements appear on the page. Mastering these concepts is essential before moving on to advanced layout techniques like **Flexbox** and **CSS Grid**.
````
