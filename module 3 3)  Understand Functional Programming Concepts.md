# 🐍 Functional Programming Concepts in Python

> Functional programming is a programming style where **functions are treated as first-class objects**. Instead of changing data directly, you create new data by applying functions.

---

# 📚 Learning Objectives

After completing this topic, you will understand:

- Higher-order functions
- `map()`
- `filter()`
- `reduce()`
- Writing reusable transformation logic
- Functional vs Procedural programming
- Advantages and disadvantages
- Common mistakes
- Interview questions

---

# What is Functional Programming?

Functional programming is a style of programming where:

- Functions are treated as values.
- Functions can be passed as arguments.
- Functions can return other functions.
- Data is transformed instead of modified.
- Functions avoid changing external variables (side effects).

Think of it like a **factory machine**:

```
Input
   ↓
Function
   ↓
Output
```

The function receives data, processes it, and returns a new result without changing the original data.

---

# Why Functional Programming?

Suppose you have a list of marks.

```
[35, 48, 60, 90]
```

You want to:

- Increase every mark by 5.
- Remove marks below 40.
- Find the total.

Instead of writing multiple loops, functional programming lets you do this using functions like:

- map()
- filter()
- reduce()

---

# 1️⃣ Higher-Order Functions

## What is a Higher-Order Function?

A **higher-order function** is a function that:

- Accepts another function as an argument, **or**
- Returns another function.

---

## Example 1

```python
def greet(name):
    return f"Hello {name}"

def display(function, value):
    print(function(value))

display(greet, "Alna")
```

Output

```
Hello Alna
```

Explanation

```
display()
      │
      ▼
calls greet()
      │
      ▼
returns "Hello Alna"
```

---

## Example 2 (Returning a Function)

```python
def multiply_by(n):

    def multiply(x):
        return x * n

    return multiply

double = multiply_by(2)

print(double(10))
```

Output

```
20
```

Here,

- `multiply_by()` returns another function.
- `double` stores that returned function.

---

# 2️⃣ map()

## What is map()?

`map()` applies the **same function** to every item in an iterable.

It returns a **map object**, so it is usually converted into a list.

---

## Syntax

```python
map(function, iterable)
```

---

## Example

```python
numbers = [1,2,3,4]

result = list(map(lambda x: x*2, numbers))

print(result)
```

Output

```
[2,4,6,8]
```

---

## Without map()

```python
numbers = [1,2,3,4]

result = []

for n in numbers:
    result.append(n*2)

print(result)
```

Same output.

---

## Another Example

Convert names to uppercase.

```python
names = ["alna","anu","tom"]

result = list(map(str.upper, names))

print(result)
```

Output

```
['ALNA','ANU','TOM']
```

---

# 3️⃣ filter()

## What is filter()?

`filter()` removes unwanted items.

It keeps only items where the condition is **True**.

---

## Syntax

```python
filter(function, iterable)
```

---

## Example

```python
numbers = [10,15,20,25,30]

result = list(filter(lambda x: x%2==0, numbers))

print(result)
```

Output

```
[10,20,30]
```

---

## Another Example

Keep only positive numbers.

```python
numbers = [-5,3,-2,7,10]

positive = list(filter(lambda x:x>0,numbers))

print(positive)
```

Output

```
[3,7,10]
```

---

# 4️⃣ reduce()

## What is reduce()?

`reduce()` combines all elements into **one final value**.

It is available in the **functools** module.

---

## Syntax

```python
from functools import reduce

reduce(function, iterable)
```

---

## Example

```python
from functools import reduce

numbers = [1,2,3,4]

total = reduce(lambda x,y:x+y,numbers)

print(total)
```

Output

```
10
```

---

## How reduce() Works

```
1 + 2 = 3

3 + 3 = 6

6 + 4 = 10
```

Final answer

```
10
```

---

## Product Example

```python
from functools import reduce

numbers=[2,3,4]

product=reduce(lambda x,y:x*y,numbers)

print(product)
```

Output

```
24
```

---

# map vs filter vs reduce

| Function | Purpose | Output |
|-----------|----------|---------|
| map() | Transform every item | New iterable |
| filter() | Keep selected items | Filtered iterable |
| reduce() | Combine items | Single value |

---

# Visual Difference

Original List

```
[1,2,3,4,5]
```

map()

```
[2,4,6,8,10]
```

filter()

```
[2,4]
```

reduce()

```
15
```

---

# 5️⃣ Writing Reusable Transformation Logic

Instead of repeating the same code in different places, write reusable functions.

---

## Bad Example

```python
numbers=[1,2,3]

print(list(map(lambda x:x*x,numbers)))

numbers2=[4,5,6]

print(list(map(lambda x:x*x,numbers2)))
```

The logic is repeated.

---

## Better Example

```python
def square(x):
    return x*x

numbers=[1,2,3]

result=list(map(square,numbers))

print(result)
```

---

## Reuse Again

```python
numbers2=[4,5,6]

result=list(map(square,numbers2))

print(result)
```

The same function is reused.

---

# Why Reusable Logic?

Benefits

- Less code
- Easier debugging
- Better readability
- Easy maintenance
- Can be reused in multiple programs

---

# 6️⃣ Functional vs Procedural Thinking

## Procedural Programming

Focuses on **steps**.

Example

```
Start

↓

Loop

↓

Condition

↓

Store

↓

Print
```

Example

```python
numbers=[1,2,3,4]

result=[]

for n in numbers:

    result.append(n*2)

print(result)
```

---

## Functional Programming

Focuses on **what should happen**, not every step.

Example

```python
numbers=[1,2,3,4]

result=list(map(lambda x:x*2,numbers))

print(result)
```

---

# Comparison

| Procedural | Functional |
|------------|------------|
| Uses loops | Uses functions |
| Changes data | Creates new data |
| More lines | Less code |
| Easy for beginners | Cleaner for data transformations |
| Step-by-step instructions | Focus on transformations |

---

# Real-Life Example

Imagine washing clothes.

### Procedural

```
Pick cloth

↓

Add soap

↓

Wash

↓

Dry

↓

Fold
```

Every step is written.

---

### Functional

```
Wash(clothes)
```

The function handles all the internal steps.

---

# When to Use Functional Programming?

Use when:

- Transforming lists
- Filtering data
- Processing datasets
- Avoiding duplicate code
- Writing clean and reusable logic

---

# Advantages

- Cleaner code
- Less repetition
- Easier testing
- Better readability
- Good for data processing
- Encourages reusable functions

---

# Disadvantages

- Can be difficult for beginners
- Too many lambda functions reduce readability
- Complex logic is better written with normal functions

---

# Common Mistakes

❌ Forgetting to convert `map()` or `filter()` into a list.

```python
print(map(lambda x:x*2,[1,2,3]))
```

Correct

```python
print(list(map(lambda x:x*2,[1,2,3])))
```

---

❌ Forgetting to import `reduce()`.

Correct

```python
from functools import reduce
```

---

❌ Writing very long lambda functions.

Use `def` when the logic becomes complex.

---

# Interview Questions

### 1. What is functional programming?

A programming style where functions are treated as first-class objects and data is transformed using functions.

---

### 2. What is a higher-order function?

A function that accepts another function as an argument or returns another function.

---

### 3. What does `map()` do?

It applies a function to every item in an iterable.

---

### 4. What does `filter()` do?

It returns only the items that satisfy a condition.

---

### 5. What does `reduce()` do?

It combines all elements into a single value.

---

### 6. Which module contains `reduce()`?

`functools`

---

### 7. Difference between `map()` and `filter()`?

- `map()` transforms every item.
- `filter()` removes unwanted items.

---

### 8. Difference between `map()` and `reduce()`?

- `map()` returns multiple transformed values.
- `reduce()` returns one final value.

---

### 9. Why is reusable transformation logic important?

Because it reduces duplicate code, improves readability, and makes maintenance easier.

---

### 10. Difference between functional and procedural programming?

| Functional | Procedural |
|------------|------------|
| Focuses on transformations | Focuses on steps |
| Uses higher-order functions | Uses loops and conditions |
| Less code | More code |
| Encourages reusable functions | Encourages sequential logic |

---

# 📝 Quick Revision

- **Higher-order function** → Takes or returns another function.
- **map()** → Transform every item.
- **filter()** → Keep items that match a condition.
- **reduce()** → Combine all items into one value.
- **Reusable transformation logic** → Write once, reuse many times.
- **Functional programming** → Focus on *what* to do.
- **Procedural programming** → Focus on *how* to do it.
- Import `reduce()` using:

```python
from functools import reduce
```

- Prefer `def` over `lambda` for complex logic.
- Functional programming is especially useful for clean, readable data processing code.
