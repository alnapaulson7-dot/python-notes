# 📋 HTML Forms & Tables

> Forms collect user input, while tables organize data into rows and columns.

---

# 📚 Contents

- HTML Tables
- Form Elements
- Input Types
- Form Validation Attributes

---

# 📊 HTML Tables

Tables are used to display data in rows and columns.

## Basic Structure

```html
<table>
    <tr>
        <th>Name</th>
        <th>Age</th>
    </tr>

    <tr>
        <td>John</td>
        <td>25</td>
    </tr>

    <tr>
        <td>Alice</td>
        <td>22</td>
    </tr>
</table>
```

---

## Table Tags

| Tag | Purpose |
|------|---------|
| `<table>` | Creates a table |
| `<tr>` | Creates a table row |
| `<th>` | Creates a table heading |
| `<td>` | Creates a table data cell |

---

## Example Output

| Name | Age |
|------|-----|
| John | 25 |
| Alice | 22 |

---

# 📝 HTML Forms

Forms are used to collect information from users.

## Basic Structure

```html
<form>

    <!-- Form Elements -->

</form>
```

---

# 🧩 Common Form Elements

## 🔹 Input

Used to accept user input.

```html
<input type="text">
```

---

## 🔹 Textarea

Used for multi-line text.

```html
<textarea></textarea>
```

Example:

```html
<textarea rows="4" cols="30"></textarea>
```

---

## 🔹 Select

Creates a drop-down list.

```html
<select>

    <option>India</option>

    <option>USA</option>

    <option>Canada</option>

</select>
```

---

## 🔹 Button

Creates a clickable button.

```html
<button>Submit</button>
```

---

# ⌨️ Input Types

Different input types are used for different kinds of data.

---

## Text

```html
<input type="text">
```

Used for names, usernames, etc.

---

## Email

```html
<input type="email">
```

Accepts only valid email addresses.

Example:

```
✅ user@gmail.com

❌ user123
```

---

## Password

```html
<input type="password">
```

Characters are hidden while typing.

---

## Radio Button

Allows the user to choose **only one** option.

```html
<input type="radio" name="gender"> Male

<input type="radio" name="gender"> Female
```

> 💡 Radio buttons must have the same `name` to work as a single-choice group.

---

## Checkbox

Allows selecting **multiple** options.

```html
<input type="checkbox"> HTML

<input type="checkbox"> CSS

<input type="checkbox"> JavaScript
```

---

## File Upload

```html
<input type="file">
```

Allows users to upload files.

---

# 📋 Input Type Summary

| Input Type | Purpose |
|------------|---------|
| `text` | Single-line text |
| `email` | Email address |
| `password` | Hidden password |
| `radio` | Select one option |
| `checkbox` | Select multiple options |
| `file` | Upload files |

---

# ✅ Form Validation Attributes

Validation helps ensure users enter correct information before submitting a form.

---

## `required`

Makes a field mandatory.

```html
<input
    type="text"
    required>
```

User cannot submit the form without filling this field.

---

## `placeholder`

Displays a hint inside an input field.

```html
<input
    type="text"
    placeholder="Enter your name">
```

---

## `pattern`

Validates input using a regular expression.

Example: Only 10-digit phone numbers.

```html
<input
    type="text"
    pattern="[0-9]{10}">
```

### Valid

```
9876543210
```

### Invalid

```
98765

abc123
```

---

# 📊 Validation Attribute Summary

| Attribute | Purpose |
|-----------|---------|
| `required` | Makes the field mandatory |
| `placeholder` | Shows hint text |
| `pattern` | Validates input format |

---

# 🎯 Complete Example

```html
<!DOCTYPE html>
<html>

<head>
    <title>Forms & Tables</title>
</head>

<body>

<h2>Student Registration</h2>

<form>

    <input
        type="text"
        placeholder="Enter your name"
        required>

    <br><br>

    <input
        type="email"
        placeholder="Enter your email"
        required>

    <br><br>

    <input
        type="password"
        placeholder="Password"
        required>

    <br><br>

    Gender

    <input type="radio" name="gender"> Male

    <input type="radio" name="gender"> Female

    <br><br>

    Skills

    <input type="checkbox"> HTML

    <input type="checkbox"> CSS

    <input type="checkbox"> JavaScript

    <br><br>

    <textarea
        rows="4"
        cols="30"
        placeholder="About Yourself">
    </textarea>

    <br><br>

    <select>

        <option>India</option>

        <option>USA</option>

        <option>Canada</option>

    </select>

    <br><br>

    <input type="file">

    <br><br>

    <button>Submit</button>

</form>

<hr>

<h2>Student Table</h2>

<table border="1">

<tr>
    <th>Name</th>
    <th>Age</th>
</tr>

<tr>
    <td>John</td>
    <td>20</td>
</tr>

<tr>
    <td>Alice</td>
    <td>22</td>
</tr>

</table>

</body>
</html>
```

---

# 💡 Quick Comparison

## Radio vs Checkbox

| Radio | Checkbox |
|--------|----------|
| Select only one option | Select multiple options |
| Same `name` groups options | Each option is independent |

---

## Input vs Textarea

| Input | Textarea |
|--------|----------|
| Single-line input | Multi-line input |
| Short text | Long text |

---

## `th` vs `td`

| `<th>` | `<td>` |
|---------|--------|
| Table heading | Table data |
| Bold & centered by default | Normal cell |

---

# ⚡ Quick Revision

✅ `<table>` → Creates a table

✅ `<tr>` → Table row

✅ `<th>` → Table heading

✅ `<td>` → Table data

✅ `<form>` → Creates a form

✅ `<input>` → User input field

✅ `<textarea>` → Multi-line text

✅ `<select>` → Drop-down list

✅ `<button>` → Button

✅ `text` → Normal text input

✅ `email` → Email input

✅ `password` → Hidden password

✅ `radio` → Single choice

✅ `checkbox` → Multiple choices

✅ `file` → Upload files

✅ `required` → Mandatory field

✅ `placeholder` → Hint text

✅ `pattern` → Validates input format

---

> 🚀 **Key Takeaway:** Tables organize data into rows and columns, while forms collect user input using various elements and input types. Validation attributes like `required`, `placeholder`, and `pattern` help ensure users enter valid information before submitting the form.
````
