# 🐍 Advanced Python Features

> These concepts help you write **shorter, cleaner, and more efficient Python code**. Mastering them will make your programs more Pythonic.

---

# 📚 Learning Objectives

After completing this topic, you will understand:

- List, Dictionary, and Set Comprehensions
- Packing and Unpacking
- *args and **kwargs
- Lambda Functions
- Iterators and Generators
- When to use each feature
- Common mistakes
- Interview questions

---

# 1️⃣ List Comprehension

## 📖 What is List Comprehension?

List comprehension is a **short and elegant way** to create a new list from an existing iterable.

Instead of writing multiple lines using a loop, you can write everything in a single line.

---

## Traditional Method

```python
numbers = [1,2,3,4,5]

squares = []

for num in numbers:
    squares.append(num * num)

print(squares)
```

Output

```
[1,4,9,16,25]
```

---

## Using List Comprehension

```python
numbers = [1,2,3,4,5]

squares = [num * num for num in numbers]

print(squares)
```

Output

```
[1,4,9,16,25]
```

---

## Syntax

```python
new_list = [expression for item in iterable]
```

---

## Example 1

```python
numbers = [1,2,3,4]

double = [x*2 for x in numbers]

print(double)
```

Output

```
[2,4,6,8]
```

---

## Example 2 (Condition)

```python
numbers = [1,2,3,4,5,6]

even = [x for x in numbers if x % 2 == 0]

print(even)
```

Output

```
[2,4,6]
```

---

## Example 3

Convert strings to uppercase

```python
names = ["alna","anu","tom"]

upper = [name.upper() for name in names]

print(upper)
```

Output

```
['ALNA','ANU','TOM']
```

---

## Advantages

✅ Less code

✅ Easy to read

✅ Faster than many traditional loops

---

# 2️⃣ Dictionary Comprehension

Dictionary comprehension creates dictionaries quickly.

---

## Syntax

```python
new_dict = {key:value for item in iterable}
```

---

## Example

```python
numbers = [1,2,3,4]

square = {x:x*x for x in numbers}

print(square)
```

Output

```
{
1:1,
2:4,
3:9,
4:16
}
```

---

## Example with Condition

```python
numbers = [1,2,3,4,5]

result = {x:x*x for x in numbers if x%2==0}

print(result)
```

Output

```
{
2:4,
4:16
}
```

---

# 3️⃣ Set Comprehension

Creates a set.

---

## Syntax

```python
new_set = {expression for item in iterable}
```

---

## Example

```python
numbers = [1,2,2,3,3,4]

unique = {x for x in numbers}

print(unique)
```

Output

```
{1,2,3,4}
```

Notice duplicate values disappear automatically.

---

# Comparison

| Type | Syntax |
|------|---------|
| List | `[ ]` |
| Dictionary | `{key:value}` |
| Set | `{ }` |

---

# 4️⃣ Packing and Unpacking

## 📖 Packing

Packing means storing multiple values inside one variable.

```python
numbers = 1,2,3,4
```

Python automatically creates

```
(1,2,3,4)
```

---

## Example

```python
data = "Alna",20,"Python"

print(data)
```

Output

```
('Alna',20,'Python')
```

---

# Unpacking

Extracting values into separate variables.

```python
name,age,course = data

print(name)
print(age)
print(course)
```

Output

```
Alna
20
Python
```

---

## Unpacking with *

```python
numbers = [1,2,3,4,5]

a,*b,c = numbers

print(a)
print(b)
print(c)
```

Output

```
1
[2,3,4]
5
```

---

# Why use Packing?

Useful when

- Returning multiple values
- Function arguments
- Swapping values

---

## Swap Variables

```python
a=10
b=20

a,b=b,a

print(a,b)
```

Output

```
20 10
```

---

# 5️⃣ *args

## What is *args?

`*args` allows a function to accept **any number of positional arguments**.

Without `*args`

```python
def add(a,b):
    return a+b
```

Can only accept two values.

---

## Using *args

```python
def add(*numbers):
    print(numbers)

add(1,2,3,4)
```

Output

```
(1,2,3,4)
```

Notice

`numbers` becomes a tuple.

---

## Sum Example

```python
def total(*numbers):

    sum=0

    for n in numbers:
        sum+=n

    return sum

print(total(10,20))
print(total(10,20,30))
print(total(10,20,30,40))
```

Output

```
30
60
100
```

---

# Rules

✔ Only one `*args`

✔ Receives positional arguments

✔ Stored as tuple

---

# 6️⃣ **kwargs

## What is **kwargs?

Allows functions to accept **any number of keyword arguments.**

---

## Example

```python
def student(**details):

    print(details)

student(name="Alna",age=20)
```

Output

```
{
'name':'Alna',
'age':20
}
```

Stored as

Dictionary

---

## Access Values

```python
def student(**details):

    print(details["name"])

student(name="Alna",age=20)
```

Output

```
Alna
```

---

# Difference

| *args | **kwargs |
|---------|------------|
| Tuple | Dictionary |
| Positional arguments | Keyword arguments |
| * | ** |

---

# 7️⃣ Lambda Functions

## 📖 What is a Lambda Function?

A **lambda function** is an anonymous (nameless) function written in a single line.

It is mainly used for **small operations** that are used only once or passed to other functions such as `map()`, `filter()`, and `sorted()`.

---

## Syntax

```python
lambda parameters: expression
```

---

## Normal Function vs Lambda

### Normal Function

```python
def square(x):
    return x * x

print(square(5))
```

Output

```
25
```

### Lambda Function

```python
square = lambda x: x * x

print(square(5))
```

Output

```
25
```

---

## Multiple Parameters

```python
add = lambda a, b: a + b

print(add(10, 20))
```

Output

```
30
```

---

## Using Lambda with `map()`

`map()` applies a function to every item in an iterable.

```python
numbers = [1,2,3,4]

result = list(map(lambda x: x * 2, numbers))

print(result)
```

Output

```
[2,4,6,8]
```

---

## Using Lambda with `filter()`

`filter()` keeps only the items that satisfy a condition.

```python
numbers = [1,2,3,4,5,6]

even = list(filter(lambda x: x % 2 == 0, numbers))

print(even)
```

Output

```
[2,4,6]
```

---

## Using Lambda with `sorted()`

```python
students = [
    ("Alna", 85),
    ("Tom", 75),
    ("Anna", 92)
]

sorted_students = sorted(students, key=lambda student: student[1])

print(sorted_students)
```

Output

```
[('Tom', 75), ('Alna', 85), ('Anna', 92)]
```

---

## When to Use Lambda

✅ Small one-time functions

✅ `map()`

✅ `filter()`

✅ `sorted()`

❌ Avoid for large or complex logic—use `def` instead.

---

# 8️⃣ Iterators

## What is an Iterator?

An **iterator** is an object that returns **one item at a time** from a collection.

It keeps track of its current position.

---

## Iterable vs Iterator

| Iterable | Iterator |
|-----------|----------|
| Can be looped over | Produces one item at a time |
| list | iterator |
| tuple | iterator |
| string | iterator |

---

## Example

```python
numbers = [10,20,30]

it = iter(numbers)

print(next(it))
print(next(it))
print(next(it))
```

Output

```
10
20
30
```

Calling `next()` again raises `StopIteration`.

---

# 9️⃣ Generators

## What is a Generator?

A **generator** is a special type of iterator.

Instead of storing all values in memory, it **generates values one at a time** using the `yield` keyword.

---

## Why Use Generators?

Imagine generating numbers from **1 to 1,000,000**.

- A list stores all numbers in memory.
- A generator creates each number only when needed.

This makes generators **memory-efficient**.

---

## Generator Example

```python
def numbers():

    yield 1
    yield 2
    yield 3

g = numbers()

print(next(g))
print(next(g))
print(next(g))
```

Output

```
1
2
3
```

---

## Generator in a Loop

```python
def count():

    for i in range(5):
        yield i

for value in count():
    print(value)
```

Output

```
0
1
2
3
4
```

---

# Iterator vs Generator

| Iterator | Generator |
|-----------|-----------|
| Uses `iter()` and `next()` | Uses `yield` |
| Manual creation | Easier to create |
| More code | Less code |
| One value at a time | One value at a time |
| Can consume more memory | Memory efficient |

---

# Common Mistakes

❌ Forgetting `list()` when using `map()` or `filter()`.

❌ Using lambda for long, complex logic.

❌ Confusing `*args` (tuple) with `**kwargs` (dictionary).

❌ Calling `next()` after the iterator is exhausted.

❌ Thinking comprehensions modify the original collection—they create a new one.

---

# Interview Questions

### 1. What is list comprehension?

A concise way to create a list using a single line of code.

---

### 2. Difference between list and set comprehension?

- List keeps duplicates and order.
- Set removes duplicates automatically.

---

### 3. What is packing and unpacking?

Packing groups multiple values into one variable, while unpacking assigns them to separate variables.

---

### 4. What is `*args`?

It collects any number of positional arguments into a tuple.

---

### 5. What is `**kwargs`?

It collects any number of keyword arguments into a dictionary.

---

### 6. What is a lambda function?

An anonymous one-line function used for short operations.

---

### 7. Difference between `return` and `yield`?

| return | yield |
|---------|--------|
| Ends the function | Pauses the function |
| Returns one value | Produces values one by one |
| Used in normal functions | Used in generators |

---

### 8. What is an iterator?

An object that returns one item at a time using `next()`.

---

### 9. What is a generator?

A special iterator created using `yield` that generates values lazily and saves memory.

---

# 📝 Quick Revision

- **List Comprehension** → Create lists in one line.
- **Dictionary Comprehension** → Create dictionaries quickly.
- **Set Comprehension** → Create sets while removing duplicates.
- **Packing** → Multiple values into one variable.
- **Unpacking** → Split values into separate variables.
- **`*args`** → Variable positional arguments (tuple).
- **`**kwargs`** → Variable keyword arguments (dictionary).
- **Lambda** → Small anonymous one-line function.
- **Iterator** → Returns one item at a time with `next()`.
- **Generator** → Uses `yield` to produce values efficiently.
