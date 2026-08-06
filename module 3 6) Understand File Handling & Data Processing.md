# 📂 File Handling & Data Processing in Python

> **File Handling** allows Python programs to **read, write, update, and manage files** stored on your computer. It is one of the most important concepts for building real-world applications because data needs to be stored even after a program stops running.

---

# 📚 Learning Objectives

After completing this topic, you will understand:

- ✅ What is File Handling?
- ✅ Reading and Writing Files
- ✅ Working with Text Files
- ✅ Working with JSON Data
- ✅ Data Parsing and Transformation
- ✅ Managing Application Data Flow
- ✅ Best Practices
- ✅ Common Mistakes
- ✅ Interview Questions

---

# 📌 What is File Handling?

File handling is the process of:

- Reading data from files
- Writing data into files
- Updating existing files
- Deleting files (using external modules)

Instead of storing information only in variables, file handling allows us to **store data permanently**.

---

## Why File Handling?

Without files

```
Program Ends

↓

Data Lost
```

With files

```
Program Ends

↓

Data Saved

↓

Available Next Time
```

Example:

- Student records
- Employee details
- Login information
- Application settings
- Reports
- Logs

---

# 📂 Types of Files

Python mainly works with two types of files.

```
Files
│
├── Text Files (.txt)
│
└── Binary Files (.jpg, .pdf, .mp3 ...)
```

In this topic, we focus mainly on **Text Files** and **JSON Files**.

---

# 📁 File Modes

| Mode | Meaning |
|------|----------|
| `"r"` | Read only |
| `"w"` | Write (creates or overwrites file) |
| `"a"` | Append data |
| `"x"` | Create new file |
| `"r+"` | Read and write |
| `"w+"` | Write and read |
| `"a+"` | Append and read |

---

# 1️⃣ Opening a File

Use the `open()` function.

## Syntax

```python
file = open("filename.txt", "mode")
```

Example

```python
file = open("data.txt", "r")
```

---

# Closing a File

Always close the file after use.

```python
file.close()
```

---

# Better Way (Recommended)

Use `with`.

```python
with open("data.txt","r") as file:

    print(file.read())
```

The file closes automatically.

---

# 2️⃣ Reading Files

## read()

Reads the entire file.

```python
with open("data.txt","r") as file:

    data = file.read()

print(data)
```

---

## readline()

Reads one line.

```python
with open("data.txt","r") as file:

    print(file.readline())
```

---

## readlines()

Reads all lines into a list.

```python
with open("data.txt","r") as file:

    lines=file.readlines()

print(lines)
```

Output

```
['Hello\n','Python\n']
```

---

# Reading Line by Line

```python
with open("data.txt") as file:

    for line in file:
        print(line.strip())
```

---

# 3️⃣ Writing Files

Use `"w"` mode.

```python
with open("data.txt","w") as file:

    file.write("Hello Python")
```

---

⚠ Important

`"w"` removes old content before writing.

---

# Appending Data

Use `"a"` mode.

```python
with open("data.txt","a") as file:

    file.write("\nWelcome")
```

Output

```
Hello Python
Welcome
```

Old content remains.

---

# Writing Multiple Lines

```python
lines = [

"Python\n",

"Java\n",

"JavaScript\n"

]

with open("languages.txt","w") as file:

    file.writelines(lines)
```

---

# Reading vs Writing

| Read | Write |
|------|--------|
| Gets data | Stores data |
| Uses `"r"` | Uses `"w"` |
| Doesn't modify file | May overwrite file |

---

# 4️⃣ Working with Text Files

Text files store plain text.

Example

```
students.txt

Alna

Tom

Anna
```

---

## Reading

```python
with open("students.txt") as file:

    print(file.read())
```

---

## Writing

```python
with open("students.txt","a") as file:

    file.write("\nRahul")
```

---

# Real-Life Uses

- Notes
- Reports
- Logs
- Attendance
- Configurations

---

# 5️⃣ Working with JSON Data

## What is JSON?

JSON stands for

**JavaScript Object Notation**

It is a lightweight format used to store and exchange data.

---

Example JSON

```json
{
    "name":"Alna",
    "age":20,
    "course":"Python"
}
```

---

# Why JSON?

- Human readable
- Easy to store
- Easy to transfer
- Used in APIs
- Supported by almost every programming language

---

# Python JSON Module

```python
import json
```

---

# Python Dictionary

```python
student = {

"name":"Alna",

"age":20

}
```

---

# Convert Dictionary → JSON

```python
import json

student = {

"name":"Alna",

"age":20

}

json_data = json.dumps(student)

print(json_data)
```

---

# Convert JSON → Dictionary

```python
import json

text='{"name":"Alna","age":20}'

student=json.loads(text)

print(student["name"])
```

Output

```
Alna
```

---

# Save JSON File

```python
import json

student={

"name":"Alna",

"age":20

}

with open("student.json","w") as file:

    json.dump(student,file,indent=4)
```

---

# Read JSON File

```python
import json

with open("student.json") as file:

    data=json.load(file)

print(data)
```

---

# JSON Functions

| Function | Purpose |
|----------|----------|
| `dump()` | Write JSON to file |
| `load()` | Read JSON from file |
| `dumps()` | Dictionary → JSON string |
| `loads()` | JSON string → Dictionary |

---

# 6️⃣ Data Parsing

## What is Parsing?

Parsing means converting raw data into a format that Python can understand.

Example

```
"25"

↓

25
```

---

Example

```python
age="20"

age=int(age)
```

---

JSON Parsing

```
JSON String

↓

Dictionary

↓

Python Object
```

---

# 7️⃣ Data Transformation

## What is Data Transformation?

Changing data from one form into another.

Example

```
alna

↓

ALNA
```

---

Example

```python
names=["alna","tom"]

upper=[name.upper() for name in names]

print(upper)
```

Output

```
['ALNA','TOM']
```

---

Another Example

```python
prices=[100,200,300]

discount=[price*0.9 for price in prices]

print(discount)
```

Output

```
[90.0,180.0,270.0]
```

---

# Why Transform Data?

- Cleaning data
- Formatting output
- Calculations
- Reports
- Data analysis

---

# 8️⃣ Managing Application Data Flow

Every application follows a flow.

```
Input

↓

Read File

↓

Parse Data

↓

Process Data

↓

Transform Data

↓

Save File

↓

Output
```

---

Example

Student Marks System

```
student.json

↓

Read

↓

Calculate Grade

↓

Update Grade

↓

Save

↓

Display Result
```

---

# Best Practices

✅ Always use `with open()`.

---

✅ Close files automatically.

---

✅ Catch file-related exceptions.

```python
try:

    with open("data.txt") as file:

        print(file.read())

except FileNotFoundError:

    print("File not found.")
```

---

✅ Validate data before processing.

---

✅ Store structured data in JSON.

---

# Common Mistakes

❌ Forgetting to close files.

---

❌ Using `"w"` when `"a"` is needed.

---

❌ Forgetting to import `json`.

---

❌ Using `json.load()` on a string instead of `json.loads()`.

---

❌ Reading a file that does not exist.

---

# Real-Life Applications

- Banking Systems
- Student Management
- Library Management
- Inventory Systems
- User Login Systems
- Configuration Files
- API Communication

---

# Interview Questions

### 1. What is file handling?

File handling is the process of reading, writing, and managing files.

---

### 2. Difference between `"r"` and `"w"` mode?

| `"r"` | `"w"` |
|---------|--------|
| Read only | Write only |
| File must exist | Creates or overwrites file |

---

### 3. Difference between `"w"` and `"a"`?

| `"w"` | `"a"` |
|---------|--------|
| Overwrites existing data | Adds new data to the end |

---

### 4. Why use `with open()`?

It automatically closes the file after use, even if an error occurs.

---

### 5. What is JSON?

A lightweight data format used for storing and exchanging structured data.

---

### 6. Difference between `dump()` and `dumps()`?

| Function | Purpose |
|----------|----------|
| `dump()` | Writes JSON to a file |
| `dumps()` | Converts a Python object to a JSON string |

---

### 7. Difference between `load()` and `loads()`?

| Function | Purpose |
|----------|----------|
| `load()` | Reads JSON from a file |
| `loads()` | Converts a JSON string to a Python object |

---

### 8. What is data parsing?

Converting raw data into a usable Python format.

---

### 9. What is data transformation?

Changing data into another useful format for processing or presentation.

---

### 10. Why is file handling important?

It allows programs to store and retrieve data permanently instead of losing it when the program ends.

---

# 📝 Quick Revision

| Concept | Remember |
|----------|----------|
| `open()` | Opens a file |
| `close()` | Closes a file |
| `"r"` | Read |
| `"w"` | Write (overwrite) |
| `"a"` | Append |
| `read()` | Entire file |
| `readline()` | One line |
| `readlines()` | All lines as a list |
| `write()` | Write text |
| `json.dump()` | Write JSON to a file |
| `json.load()` | Read JSON from a file |
| `json.dumps()` | Python object → JSON string |
| `json.loads()` | JSON string → Python object |
| Parsing | Convert raw data to usable data |
| Transformation | Modify data into another form |

---

# 🎯 Summary

- **File handling** lets programs read, write, and manage persistent data.
- Use **`with open()`** to safely work with files.
- **Text files** store plain text, while **JSON files** store structured data.
- The `json` module helps convert between Python objects and JSON.
- **Data parsing** converts raw data into usable Python objects.
- **Data transformation** modifies data for processing or presentation.
- A typical application reads data, processes it, transforms it, and saves the results.
- Following best practices like handling exceptions and validating data makes applications more reliable.
