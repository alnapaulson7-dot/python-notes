# 📋 HTML Forms & Tables

> **HTML Tables** are used to organize data into rows and columns, while **HTML Forms** allow users to enter and submit information such as login details, registrations, feedback, and file uploads.

---

# 📚 Contents

- HTML Tables
- Table Structure
- HTML Forms
- Form Elements
- Input Types
- Form Validation
- Complete Example

---

# 📊 HTML Tables

A table is used to display data in a **structured format** using rows and columns.

### Common Uses

- Student Records
- Product Lists
- Employee Details
- Timetables
- Reports

---

# 🏗️ Table Structure

Every HTML table is built using four main tags.

```html
<table>

    <tr>
        <th>Name</th>
        <th>Age</th>
    </tr>

    <tr>
        <td>John</td>
        <td>22</td>
    </tr>

</table>
```

---

## 📌 Table Tags

| Tag | Full Form | Purpose |
|------|-----------|---------|
| `<table>` | Table | Creates the table |
| `<tr>` | Table Row | Creates a row |
| `<th>` | Table Header | Creates a heading cell |
| `<td>` | Table Data | Creates a normal data cell |

---

## Example Output

| Name | Age |
|------|-----|
| John | 22 |
| Alice | 20 |

---

## Difference Between `<th>` and `<td>`

| `<th>` | `<td>` |
|---------|---------|
| Table Heading | Table Data |
| Bold & Centered (default) | Normal Text |
| Usually First Row | Used for Data |

---

## Adding Borders

```html
<table border="1">
```

> 💡 **Note:** The `border` attribute is useful for learning, but in modern websites borders are usually added with **CSS**.

---

# 📝 HTML Forms

Forms allow users to **enter, edit, and submit information**.

Common examples include:

- Login Form
- Registration Form
- Contact Form
- Feedback Form
- Search Box

A form begins with the `<form>` tag.

```html
<form>

    <!-- Form Elements -->

</form>
```

---

# 🧩 Form Elements

## 🔹 `<input>`

The most commonly used form element.

Used to collect different types of user input.

```html
<input type="text">
```

---

## 🔹 `<textarea>`

Used for **multi-line text**.

Ideal for:

- Comments
- Feedback
- Address
- Description

```html
<textarea rows="4" cols="30"></textarea>
```

---

## 🔹 `<select>`

Creates a **drop-down list**.

```html
<select>

    <option>India</option>

    <option>USA</option>

    <option>Canada</option>

</select>
```

---

## 🔹 `<button>`

Creates a clickable button.

```html
<button>Submit</button>
```

Buttons can be used to:

- Submit forms
- Reset forms
- Trigger JavaScript

---

# ⌨️ Input Types

The `<input>` element becomes different controls based on its `type` attribute.

---

## 1️⃣ Text

Used for normal text.

```html
<input type="text">
```

Example

- Name
- Username
- City

---

## 2️⃣ Email

Accepts only valid email addresses.

```html
<input type="email">
```

Valid

```
user@gmail.com
```

Invalid

```
user123
```

> ✅ Browsers automatically validate the email format before form submission.

---

## 3️⃣ Password

Hides characters while typing.

```html
<input type="password">
```

Example

```
********
```

---

## 4️⃣ Radio Button

Allows selecting **only one** option from a group.

```html
<input
type="radio"
name="gender">

Male

<input
type="radio"
name="gender">

Female
```

> 💡 Radio buttons must share the same `name` attribute so that only one option can be selected.

---

## 5️⃣ Checkbox

Allows selecting **multiple** options.

```html
<input type="checkbox"> HTML

<input type="checkbox"> CSS

<input type="checkbox"> JavaScript
```

Unlike radio buttons, multiple checkboxes can be selected at the same time.

---

## 6️⃣ File Upload

Allows users to upload files.

```html
<input type="file">
```

Common uses:

- Resume Upload
- Profile Picture
- Documents
- Images

---

## 📊 Input Type Summary

| Type | Purpose | Example |
|------|---------|---------|
| `text` | Normal text | Name |
| `email` | Email address | user@gmail.com |
| `password` | Hidden password | Login |
| `radio` | Single choice | Gender |
| `checkbox` | Multiple choices | Skills |
| `file` | Upload files | Resume |

---

# ✅ Form Validation

Validation ensures users enter the correct information **before the form is submitted**.

HTML5 provides built-in validation attributes, reducing the need for JavaScript for basic checks.

---

## 🔹 `required`

Makes a field mandatory.

```html
<input
type="text"
required>
```

If left empty, the browser prevents form submission.

---

## 🔹 `placeholder`

Displays hint text inside an input field.

```html
<input
type="text"
placeholder="Enter your name">
```

Example

```
Enter your name
```

The hint disappears once the user starts typing.

---

## 🔹 `pattern`

Checks whether the input matches a specific format using a **Regular Expression (Regex)**.

Example

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

abcdef

123ABC
```

> 💡 `pattern="[0-9]{10}"` means **exactly 10 digits**.

---

## Validation Summary

| Attribute | Purpose |
|-----------|---------|
| `required` | Field cannot be left empty |
| `placeholder` | Shows hint text |
| `pattern` | Validates the input format |

---

# 💻 Complete Example

```html
<!DOCTYPE html>
<html>

<head>
    <title>Registration Form</title>
</head>

<body>

<h2>Student Registration</h2>

<form>

<label>Name</label><br>
<input
type="text"
placeholder="Enter your name"
required>

<br><br>

<label>Email</label><br>
<input
type="email"
placeholder="Enter your email"
required>

<br><br>

<label>Password</label><br>
<input
type="password"
placeholder="Enter password"
required>

<br><br>

<label>Gender</label><br>

<input
type="radio"
name="gender"> Male

<input
type="radio"
name="gender"> Female

<br><br>

<label>Skills</label><br>

<input type="checkbox"> HTML

<input type="checkbox"> CSS

<input type="checkbox"> JavaScript

<br><br>

<label>Country</label><br>

<select>

<option>India</option>

<option>USA</option>

<option>Canada</option>

</select>

<br><br>

<label>About Yourself</label><br>

<textarea
rows="4"
cols="30"
placeholder="Write something...">
</textarea>

<br><br>

<label>Upload Resume</label><br>

<input type="file">

<br><br>

<button>Submit</button>

</form>

<hr>

<h2>Student Details</h2>

<table border="1">

<tr>
<th>Name</th>
<th>Age</th>
<th>Course</th>
</tr>

<tr>
<td>John</td>
<td>22</td>
<td>Python</td>
</tr>

<tr>
<td>Alice</td>
<td>20</td>
<td>Java</td>
</tr>

</table>

</body>

</html>
```

---

# 💡 Best Practices

✅ Always use `<label>` for input fields to improve accessibility.

✅ Use `required` for mandatory fields.

✅ Choose the correct input type (`email`, `password`, etc.) for better browser validation.

✅ Group related radio buttons using the same `name` attribute.

✅ Use placeholder text only as a hint, not as a replacement for labels.

✅ Organize long forms with proper spacing and headings.

---

# ⚠️ Common Mistakes

❌ Forgetting the `<form>` tag.

❌ Using `type="text"` for email fields instead of `type="email"`.

❌ Giving different `name` values to radio buttons in the same group.

❌ Forgetting to close table rows (`</tr>`).

❌ Using `<th>` for normal data instead of headings.

❌ Relying only on HTML validation—server-side validation is still essential in real-world applications.

---

# ⚡ Quick Revision

| Element / Attribute | Purpose |
|---------------------|---------|
| `<table>` | Creates a table |
| `<tr>` | Table row |
| `<th>` | Table heading |
| `<td>` | Table data |
| `<form>` | Creates a form |
| `<input>` | User input field |
| `<textarea>` | Multi-line text |
| `<select>` | Drop-down list |
| `<option>` | Item inside a drop-down |
| `<button>` | Clickable button |
| `text` | Single-line text input |
| `email` | Email input |
| `password` | Password input |
| `radio` | Single-choice selection |
| `checkbox` | Multiple-choice selection |
| `file` | File upload |
| `required` | Mandatory field |
| `placeholder` | Hint text |
| `pattern` | Input format validation |

---

# 🚀 Key Takeaway

HTML **tables** organize information into rows and columns, making data easy to read. HTML **forms** collect user input through elements like `input`, `textarea`, `select`, and `button`. By choosing the correct **input types** and using validation attributes such as `required`, `placeholder`, and `pattern`, you can create forms that are user-friendly, accessible, and capable of performing basic input validation before submission.
````
