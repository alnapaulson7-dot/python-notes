# 🐍 Python Core Concepts

## 📚 Learning Objectives

After completing this topic, you should understand:

- Scope and variable lifetime
- Mutable vs Immutable objects
- Reference behavior in Python
- Execution flow and memory basics

---

# 1️⃣ Scope and Variable Lifetime

## 📖 What is Scope?

**Scope** is the area of a program where a variable can be accessed.

A variable is only available inside the scope where it is created.

---

## Types of Scope

### 1. Local Scope

- Created inside a function.
- Accessible only inside that function.
- Destroyed after the function finishes.

### Example

```python
def greet():
    name = "Alna"
    print(name)

greet()
```

**Output**

```
Alna
```

❌ This will cause an error:

```python
print(name)
```

Reason: `name` exists only inside `greet()`.

---

### 2. Global Scope

- Created outside all functions.
- Can be accessed from anywhere in the program.

### Example

```python
name = "Alna"

def show():
    print(name)

show()
print(name)
```

**Output**

```
Alna
Alna
```

---

## Variable Lifetime

Variable lifetime means **how long a variable exists in memory.**

### Local Variable

- Created when the function starts.
- Destroyed when the function ends.

### Global Variable

- Created when the program starts.
- Exists until the program ends.

---

## Summary

| Scope | Created | Accessible | Lifetime |
|--------|----------|------------|----------|
| Local | Inside function | Inside function only | Until function ends |
| Global | Outside function | Entire program | Until program ends |

---

# 2️⃣ Mutable vs Immutable

## 📖 What does Mutable mean?

Mutable objects **can be changed after they are created.**

Examples:

- List
- Dictionary
- Set

### Example

```python
numbers = [1, 2, 3]

numbers.append(4)

print(numbers)
```

**Output**

```
[1, 2, 3, 4]
```

The same list is modified.

---

## 📖 What does Immutable mean?

Immutable objects **cannot be changed after creation.**

Examples:

- Integer
- Float
- String
- Tuple
- Boolean

### Example

```python
text = "Python"

text = text + " Full Stack"

print(text)
```

**Output**

```
Python Full Stack
```

A **new string** is created.

---

## Mutable vs Immutable

| Mutable | Immutable |
|----------|------------|
| Can change | Cannot change |
| Same object modified | New object created |
| list | int |
| dict | float |
| set | string |
| | tuple |
| | bool |

---

# 3️⃣ Reference Behavior in Python

## 📖 What is a Reference?

Variables do **not store the object itself.**

They store a **reference (memory address)** to the object.

Example:

```
Variable
   │
   ▼
Memory
[10]
```

---

## Example

```python
a = [1, 2, 3]
b = a
```

Memory representation

```
a ─────► [1,2,3]
b ─────►
```

Both variables refer to the **same list**.

---

### Modify one variable

```python
b.append(4)

print(a)
print(b)
```

**Output**

```
[1,2,3,4]
[1,2,3,4]
```

Why?

Because both variables point to the **same object**.

---

## Creating a Copy

```python
a = [1,2,3]

b = a.copy()

b.append(4)

print(a)
print(b)
```

Output

```
[1,2,3]
[1,2,3,4]
```

Now both variables refer to **different objects**.

---

# 4️⃣ Execution Flow and Memory Basics

## Program Execution Flow

Python executes code **line by line** from top to bottom.

Example

```python
x = 10

y = 20

z = x + y

print(z)
```

Execution order

```
Step 1 → x = 10

Step 2 → y = 20

Step 3 → z = x + y

Step 4 → print(z)
```

Output

```
30
```

---

# Memory Basics

When a variable is created:

1. Python creates an object in memory.
2. The variable stores the object's reference.
3. Python reuses objects whenever possible.
4. Unused objects are removed automatically by the **Garbage Collector**.

Example

```python
a = 10
b = a
```

Memory

```
a ───► 10
b ───► 10
```

Both reference the same integer object.

---

## Important Points

✅ Variables store references.

✅ Lists are mutable.

✅ Strings are immutable.

✅ Functions create local scope.

✅ Python executes code from top to bottom.

✅ Local variables disappear after the function finishes.

---

# Common Mistakes

❌ Assuming variables store actual values.

❌ Modifying one list without realizing another variable references it.

❌ Trying to access a local variable outside a function.

❌ Forgetting to use `.copy()` when creating a separate list.

---

# Interview Questions

### 1. What is scope in Python?

Scope is the region where a variable can be accessed.

---

### 2. What is the difference between local and global variables?

- Local variables exist inside functions.
- Global variables exist throughout the program.

---

### 3. What are mutable objects?

Objects that can be modified after creation.

Examples:
- List
- Dictionary
- Set

---

### 4. What are immutable objects?

Objects that cannot be modified after creation.

Examples:
- int
- float
- string
- tuple

---

### 5. What is reference behavior?

Variables hold references to objects in memory rather than storing the objects themselves.

---

### 6. Why does changing one list sometimes change another?

Because both variables refer to the same list object.

---

# Quick Revision

- Scope → Where a variable is accessible.
- Variable Lifetime → How long a variable exists.
- Mutable → Can be changed.
- Immutable → Cannot be changed.
- Reference → Variable points to an object.
- `.copy()` → Creates a separate copy of a list.
- Execution Flow → Python runs code line by line.
- Garbage Collector → Removes unused objects from memory.
