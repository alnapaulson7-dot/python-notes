# ⚡ Asynchronous & Concurrent Programming in Python

> **Asynchronous Programming** allows a program to perform **multiple tasks efficiently without waiting for one task to finish before starting another**. It is mainly used for **I/O-bound operations** such as network requests, file handling, and database queries.

---

# 📚 Learning Objectives

After completing this topic, you will understand:

- ✅ Synchronous vs Asynchronous Execution
- ✅ Concurrency vs Parallelism
- ✅ Basic Idea of Async Programming
- ✅ `async` Keyword
- ✅ `await` Keyword
- ✅ Event Loop
- ✅ Real-World Use Cases
- ✅ Best Practices
- ✅ Common Mistakes
- ✅ Interview Questions

---

# 🏗️ Async Programming Overview

```
Python Program
│
├── Synchronous Execution
│
├── Asynchronous Execution
│
├── Event Loop
│
├── async
│
├── await
│
└── Concurrent Tasks
```

---

# 📖 What is Synchronous Execution?

In **synchronous programming**, tasks are executed **one after another**.

The next task starts **only after** the current task finishes.

---

## Flow

```
Task 1

↓

Task 2

↓

Task 3

↓

Program Ends
```

---

## Example

```python
print("Task 1")

print("Task 2")

print("Task 3")
```

Output

```
Task 1
Task 2
Task 3
```

Each statement waits for the previous one.

---

# Real-Life Example

Imagine standing in a bank queue.

```
Customer 1

↓

Customer 2

↓

Customer 3
```

Everyone waits for the previous customer.

This is **Synchronous Programming**.

---

# Advantages

- Easy to understand
- Easy to debug
- Predictable execution

---

# Disadvantages

- Slow for long-running tasks
- Wastes time while waiting
- Poor performance for I/O operations

---

# 📖 What is Asynchronous Execution?

In **asynchronous programming**, a task can **pause while waiting**, allowing another task to run.

Instead of blocking the program, Python switches to another available task.

---

## Flow

```
Task 1 Starts

↓

Waiting...

↓

Task 2 Runs

↓

Task 3 Runs

↓

Task 1 Continues
```

---

# Real-Life Example

Ordering food at a restaurant.

```
Place Order

↓

Food Cooking

↓

Talk with Friends

↓

Food Ready

↓

Eat
```

You don't stand idle while the food is cooking.

This is similar to **Asynchronous Programming**.

---

# Synchronous vs Asynchronous

| Synchronous | Asynchronous |
|-------------|--------------|
| One task at a time | Multiple waiting tasks can progress |
| Blocking | Non-blocking |
| Simpler | More efficient for I/O |
| Waits for each task | Switches to other tasks while waiting |

---

# 📖 What is Concurrency?

**Concurrency** means **handling multiple tasks during the same period**.

Tasks may not run at the exact same instant, but they **make progress together**.

---

## Example

```
Download File

↓

Read Email

↓

Check Messages

↓

Continue Download
```

The tasks overlap.

---

# 📖 What is Parallelism?

Parallelism means **multiple tasks actually run at the same time**, usually on different CPU cores.

---

# Concurrency vs Parallelism

| Concurrency | Parallelism |
|-------------|-------------|
| Multiple tasks make progress together | Multiple tasks execute simultaneously |
| Often uses one CPU core | Usually uses multiple CPU cores |
| Great for I/O-bound work | Great for CPU-bound work |

---

# 📖 What is Async Programming?

Async programming allows Python to perform useful work while waiting for slow operations like:

- Network requests
- File reading
- Database queries
- API calls

Instead of waiting, another task runs.

---

# Event Loop

The **Event Loop** is the engine that manages asynchronous tasks.

```
Task Ready?

↓

Yes

↓

Run Task

↓

Waiting?

↓

Run Another Task
```

Python uses the **asyncio** module for asynchronous programming.

---

# 1️⃣ async Keyword

The `async` keyword is used to define an **asynchronous function** (also called a coroutine).

---

## Syntax

```python
async def greet():

    print("Hello")
```

---

## Example

```python
async def hello():

    print("Welcome")
```

This function is asynchronous but **does not execute until awaited or scheduled**.

---

# 2️⃣ await Keyword

The `await` keyword pauses the current async function until another async task completes.

During the wait, Python can execute other asynchronous tasks.

---

## Syntax

```python
await task()
```

---

## Example

```python
import asyncio

async def greet():

    await asyncio.sleep(2)

    print("Hello")

asyncio.run(greet())
```

Output (after 2 seconds)

```
Hello
```

---

# Understanding `async` and `await`

```
async

↓

Creates Async Function

↓

await

↓

Wait for Task

↓

Run Other Tasks

↓

Continue Execution
```

---

# Running Multiple Async Tasks

```python
import asyncio

async def task1():

    await asyncio.sleep(2)

    print("Task 1 Finished")

async def task2():

    await asyncio.sleep(1)

    print("Task 2 Finished")

async def main():

    await asyncio.gather(
        task1(),
        task2()
    )

asyncio.run(main())
```

Possible Output

```
Task 2 Finished
Task 1 Finished
```

Both tasks run concurrently.

---

# Why Use `asyncio.sleep()`?

Unlike `time.sleep()`, `asyncio.sleep()` **does not block** the event loop.

| `time.sleep()` | `asyncio.sleep()` |
|----------------|-------------------|
| Blocks the program | Allows other async tasks to run |
| Used in synchronous code | Used in asynchronous code |

---

# Real-World Use Cases

## 🌐 Web Applications

- Handle multiple user requests
- API servers

---

## 📡 API Requests

Fetching data from multiple websites simultaneously.

---

## 🗄️ Database Operations

Waiting for database responses without freezing the application.

---

## 📁 File Processing

Reading and writing multiple files efficiently.

---

## 💬 Chat Applications

Messaging apps like WhatsApp or Telegram.

---

## 🎮 Online Games

Managing multiple player actions.

---

## ☁️ Cloud Services

Handling thousands of simultaneous requests.

---

# When to Use Async

Use asynchronous programming when:

- Making HTTP requests
- Downloading files
- Uploading files
- Database queries
- Waiting for user input
- Communicating with external services

---

# When NOT to Use Async

Avoid async for:

- Heavy mathematical calculations
- Image processing
- Video rendering
- CPU-intensive tasks

For these, use multiprocessing or multithreading.

---

# Best Practices

✅ Use async only for I/O-bound tasks.

---

✅ Keep async functions focused on one responsibility.

---

✅ Use `await` when calling another async function.

---

✅ Use `asyncio.gather()` to run independent async tasks concurrently.

---

✅ Avoid blocking functions like `time.sleep()` inside async code.

---

# Common Mistakes

❌ Forgetting `await`.

```python
greet()
```

Correct

```python
await greet()
```

---

❌ Calling async functions from normal code without an event loop.

---

❌ Mixing `time.sleep()` inside async functions.

---

❌ Using async for CPU-heavy tasks.

---

# Real-Life Comparison

## Synchronous

```
Wash Clothes

↓

Wait

↓

Cook Food

↓

Wait

↓

Watch TV
```

---

## Asynchronous

```
Start Washing Machine

↓

Cook Food

↓

Watch TV

↓

Clothes Finished
```

Time is used more efficiently.

---

# Advantages

- Better responsiveness
- Efficient use of waiting time
- Handles many I/O operations
- Scalable applications
- Improved performance for network-based programs

---

# Disadvantages

- Harder to understand for beginners
- Debugging can be more complex
- Not useful for CPU-intensive work

---

# Interview Questions

### 1. What is asynchronous programming?

A programming approach where tasks can pause while waiting, allowing other tasks to run.

---

### 2. What is the difference between synchronous and asynchronous execution?

| Synchronous | Asynchronous |
|-------------|--------------|
| Executes one task at a time | Allows other tasks to progress while waiting |
| Blocking | Non-blocking |

---

### 3. What is concurrency?

Handling multiple tasks during the same period, even if they are not running simultaneously.

---

### 4. What is parallelism?

Executing multiple tasks at the exact same time using multiple CPU cores.

---

### 5. What does the `async` keyword do?

It defines an asynchronous function (coroutine).

---

### 6. What does `await` do?

It pauses an async function until another async task completes while allowing other tasks to run.

---

### 7. What is the event loop?

The event loop schedules and manages asynchronous tasks in Python.

---

### 8. Which module is commonly used for async programming?

`asyncio`

---

### 9. When should you use asynchronous programming?

For I/O-bound operations like API calls, file handling, and database access.

---

### 10. When should you avoid asynchronous programming?

For CPU-intensive tasks such as heavy calculations, image processing, or video rendering.

---

# 📝 Quick Revision

| Concept | Remember |
|----------|----------|
| Synchronous | One task at a time |
| Asynchronous | Non-blocking execution |
| Concurrency | Multiple tasks make progress together |
| Parallelism | Multiple tasks run simultaneously |
| `async` | Defines an asynchronous function |
| `await` | Waits without blocking the event loop |
| Event Loop | Manages async tasks |
| `asyncio` | Python module for async programming |
| `asyncio.gather()` | Runs multiple async tasks concurrently |

---

# 🎯 Summary

- **Synchronous execution** performs tasks one after another.
- **Asynchronous execution** allows other tasks to run while waiting for slow operations.
- **Concurrency** means multiple tasks make progress during the same period, while **parallelism** means tasks truly run at the same time.
- The **`async`** keyword defines asynchronous functions, and **`await`** pauses them without blocking other tasks.
- Python's **`asyncio`** module provides the event loop and tools for asynchronous programming.
- Async programming is ideal for **I/O-bound tasks** such as network requests, file operations, and database access, but not for CPU-intensive work.
