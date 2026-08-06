# 🛡️ Exception Handling & Debugging in Python

> **Exception Handling** is the process of handling runtime errors so that the program does **not crash unexpectedly**. It allows the program to continue running or exit gracefully with meaningful error messages.

---

# 📚 Learning Objectives

After completing this topic, you will understand:

- ✅ What are Exceptions?
- ✅ Why Exception Handling is important
- ✅ `try`, `except`, `else`, `finally`, and `raise`
- ✅ Creating Custom Exceptions (Basic Idea)
- ✅ Reading Stack Traces
- ✅ Debugging Techniques
- ✅ Writing Safe and Predictable Code
- ✅ Best Practices
- ✅ Common Mistakes
- ✅ Interview Questions

---

# 🏗️ Exception Handling Flow

```
Program Starts
      │
      ▼
 Execute Code
      │
      ▼
Exception Occurred?
      │
 ┌────┴────┐
 │         │
No        Yes
 │         │
 ▼         ▼
Continue  except Block
 │         │
 └────┬────┘
      ▼
 finally Block
      ▼
Program Ends
```

---

# 1️⃣ What is an Exception?

An **exception** is an error that occurs while a program is running.

If an exception is not handled, Python stops the program.

---

## Example

```python
num = 10

print(num / 0)
```

Output

```
ZeroDivisionError: division by zero
```

The program crashes because division by zero is not allowed.

---

# Why Handle Exceptions?

Without exception handling:

- Program stops immediately.
- Remaining code is not executed.
- Poor user experience.

With exception handling:

- Prevents crashes.
- Displays meaningful error messages.
- Allows the program to continue safely.

---

# Common Exceptions

| Exception | Cause |
|-----------|-------|
| `ZeroDivisionError` | Dividing by zero |
| `ValueError` | Invalid value |
| `TypeError` | Wrong data type |
| `IndexError` | Invalid list index |
| `KeyError` | Missing dictionary key |
| `FileNotFoundError` | File does not exist |
| `NameError` | Variable not defined |

---

# 2️⃣ try

The `try` block contains code that **may cause an exception**.

---

## Syntax

```python
try:
    # Risky code
```

---

## Example

```python
try:
    print(10 / 0)
```

Python watches the code inside `try`.

---

# 3️⃣ except

The `except` block runs **only if an exception occurs**.

---

## Syntax

```python
try:
    risky_code

except:
    handle_error
```

---

## Example

```python
try:
    print(10 / 0)

except:
    print("Cannot divide by zero.")
```

Output

```
Cannot divide by zero.
```

The program does not crash.

---

# Catching Specific Exceptions

Instead of catching every error, catch only the required exception.

```python
try:
    print(10 / 0)

except ZeroDivisionError:
    print("Division by zero is not allowed.")
```

---

## Multiple Exceptions

```python
try:
    number = int(input("Enter a number: "))
    print(10 / number)

except ValueError:
    print("Please enter a valid integer.")

except ZeroDivisionError:
    print("Zero is not allowed.")
```

---

# 4️⃣ else

The `else` block executes **only if no exception occurs**.

---

## Example

```python
try:
    number = int(input("Enter a number: "))
    print(10 / number)

except ZeroDivisionError:
    print("Cannot divide by zero.")

else:
    print("Calculation completed successfully.")
```

---

# 5️⃣ finally

The `finally` block **always executes**, whether an exception occurs or not.

Useful for:

- Closing files
- Closing database connections
- Releasing resources

---

## Example

```python
try:
    print(10 / 0)

except ZeroDivisionError:
    print("Error occurred.")

finally:
    print("Program Finished.")
```

Output

```
Error occurred.
Program Finished.
```

---

# Execution Order

```
try

↓

Exception?

↓

except

↓

finally
```

If there is **no exception**:

```
try

↓

else

↓

finally
```

---

# 6️⃣ raise

The `raise` keyword is used to **manually create an exception**.

---

## Syntax

```python
raise ExceptionType("Message")
```

---

## Example

```python
age = 15

if age < 18:
    raise ValueError("Age must be 18 or above.")
```

Output

```
ValueError: Age must be 18 or above.
```

---

# Why Use raise?

Use `raise` when:

- Invalid data is entered.
- Business rules are violated.
- You want to stop execution with a meaningful error.

---

# Example

```python
marks = -5

if marks < 0:
    raise ValueError("Marks cannot be negative.")
```

---

# 7️⃣ Custom Exceptions (Basic Idea)

Python allows you to create your own exception classes.

Custom exceptions make programs more meaningful.

---

## Syntax

```python
class MyError(Exception):
    pass
```

---

## Example

```python
class InvalidAgeError(Exception):
    pass

age = 15

if age < 18:
    raise InvalidAgeError("Age must be at least 18.")
```

---

## Why Custom Exceptions?

Instead of

```
ValueError
```

You can create

```
InvalidAgeError
```

which clearly explains the problem.

---

# 8️⃣ Reading Stack Traces

When Python encounters an unhandled exception, it prints a **stack trace**.

A stack trace shows:

- Where the error occurred.
- Which line caused the error.
- What type of error occurred.

---

## Example

```python
numbers = [10,20]

print(numbers[5])
```

Output

```
Traceback (most recent call last):

File "main.py", line 3

IndexError: list index out of range
```

---

## Understanding the Stack Trace

```
Traceback

↓

File Name

↓

Line Number

↓

Error Type

↓

Error Message
```

---

# Example

```python
name = "Python"

print(name + 10)
```

Output

```
TypeError:
can only concatenate str (not "int")
```

The stack trace tells you exactly what went wrong.

---

# 9️⃣ Debugging

## What is Debugging?

Debugging is the process of **finding and fixing errors** in a program.

---

# Types of Errors

## 1. Syntax Error

Wrong Python grammar.

```python
if x == 10

print(x)
```

---

## 2. Runtime Error

Occurs while the program is running.

```python
10 / 0
```

---

## 3. Logical Error

Program runs successfully but produces incorrect output.

```python
print(10 - 5)
```

when addition was expected.

---

# Debugging Techniques

### 1. Read the Error Message

Python usually explains the problem.

---

### 2. Check the Line Number

Go directly to the line shown in the stack trace.

---

### 3. Use print()

```python
print(value)
```

to inspect variable values.

---

### 4. Test Small Parts

Run small sections of code instead of the whole program.

---

### 5. Use Meaningful Variable Names

Bad

```python
a = 10
```

Better

```python
student_age = 10
```

---

# 10️⃣ Writing Predictable and Safe Logic

Good programs should:

- Handle unexpected input.
- Avoid crashes.
- Validate data before processing.
- Display useful error messages.

---

## Example

```python
try:

    age = int(input("Enter age: "))

    if age < 0:
        raise ValueError("Age cannot be negative.")

    print("Age:", age)

except ValueError as error:

    print(error)

finally:

    print("Program Finished.")
```

---

# Best Practices

✅ Catch specific exceptions.

```python
except ValueError:
```

Instead of

```python
except:
```

---

✅ Use `finally` to release resources.

---

✅ Validate user input.

---

✅ Use custom exceptions for business rules.

---

✅ Keep `try` blocks small.

---

# Common Mistakes

❌ Using a blank `except`.

```python
except:
```

Always catch specific exceptions.

---

❌ Ignoring error messages.

Read the stack trace carefully.

---

❌ Writing very large `try` blocks.

Only include risky code.

---

❌ Not using `finally` when working with files.

---

❌ Raising exceptions without meaningful messages.

---

# Real-Life Example

Think of driving a car.

```
Driving

↓

Problem?

↓

Brake

↓

Fix

↓

Continue Driving
```

Exception handling works similarly.

---

# Advantages

- Prevents crashes.
- Makes programs reliable.
- Easier debugging.
- Better user experience.
- Cleaner code.

---

# Interview Questions

### 1. What is an exception?

An error that occurs during program execution.

---

### 2. What is the purpose of `try`?

To write code that may generate an exception.

---

### 3. What does `except` do?

Handles exceptions when they occur.

---

### 4. What is the purpose of `finally`?

Runs whether an exception occurs or not.

---

### 5. What does `raise` do?

Creates an exception manually.

---

### 6. What is a custom exception?

A user-defined exception class created by inheriting from `Exception`.

---

### 7. What is a stack trace?

A report showing where an error occurred and what caused it.

---

### 8. What is debugging?

The process of finding and fixing errors in a program.

---

### 9. Difference between Syntax Error and Runtime Error?

| Syntax Error | Runtime Error |
|---------------|---------------|
| Incorrect Python syntax | Occurs while the program is running |
| Program won't start | Program starts but crashes |

---

### 10. Why should you catch specific exceptions?

Because it makes error handling more accurate and easier to maintain.

---

# 📝 Quick Revision

| Concept | Remember |
|----------|----------|
| `try` | Code that may fail |
| `except` | Handle errors |
| `else` | Runs if no error occurs |
| `finally` | Always executes |
| `raise` | Create an exception manually |
| Custom Exception | Create your own error class |
| Stack Trace | Shows where the error occurred |
| Debugging | Finding and fixing errors |
| Safe Logic | Validate input and handle exceptions properly |

---

# 🎯 Summary

- An **exception** is an error that occurs during program execution.
- Use **`try`** to write risky code and **`except`** to handle errors.
- **`else`** runs when no exception occurs, while **`finally`** always executes.
- Use **`raise`** to manually generate exceptions.
- Create **custom exceptions** for application-specific errors.
- Read **stack traces** carefully to locate and understand errors.
- **Debugging** helps identify and fix syntax, runtime, and logical errors.
- Writing **safe and predictable logic** improves reliability, readability, and user experience.
