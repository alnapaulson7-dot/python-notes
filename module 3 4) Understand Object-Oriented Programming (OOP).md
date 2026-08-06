# 🐍 Object-Oriented Programming (OOP) in Python

> Object-Oriented Programming (OOP) is a programming paradigm that organizes code into **classes** and **objects**. It helps developers write **clean, reusable, modular, and maintainable** code.

---

# 📚 Learning Objectives

By the end of this topic, you will understand:

- ✅ Classes and Objects
- ✅ Constructors (`__init__`)
- ✅ Instance Variables
- ✅ Inheritance
- ✅ Encapsulation
- ✅ Polymorphism
- ✅ Organizing Code Using OOP
- ✅ Advantages of OOP
- ✅ Common Mistakes
- ✅ Interview Questions

---

# 🏗️ OOP Architecture

```
                    Object-Oriented Programming
                              │
        ┌─────────────────────┼─────────────────────┐
        │                     │                     │
     Classes              Objects            Constructors
        │                     │                     │
        ├──────────────┬──────┴─────────────┐
        │              │                    │
 Instance Variables  Inheritance    Encapsulation
                                           │
                                    Polymorphism
```

---

# 1️⃣ Classes and Objects

## 📖 What is a Class?

A **class** is a **blueprint (template)** used to create objects.

A class defines:

- Variables (Attributes)
- Functions (Methods)

Think of a class as the **design of a house**.

The design itself is not a house.

---

## 📖 What is an Object?

An **object** is a real instance of a class.

Example

```
Blueprint  → Class

House      → Object
```

One class can create many objects.

---

## Syntax

```python
class Student:
    pass
```

---

## Creating an Object

```python
class Student:

    def greet(self):
        print("Welcome")

student = Student()

student.greet()
```

Output

```
Welcome
```

---

## Multiple Objects

```python
s1 = Student()
s2 = Student()
s3 = Student()
```

Every object has its own identity.

---

## Real-Life Example

```
Class

Car

↓

Objects

BMW
Audi
Tesla
Toyota
```

---

## Class vs Object

| Class | Object |
|---------|---------|
| Blueprint | Real Instance |
| Template | Created from class |
| Created once | Can create many |
| Defines properties | Stores actual values |

---

# 2️⃣ Constructors and Instance Variables

## 📖 What is a Constructor?

A constructor is a **special method** that runs automatically when an object is created.

Python constructor:

```python
__init__()
```

---

## Why Use Constructors?

Without constructor

```python
student.name="Alna"
student.age=20
```

With constructor

```python
Student("Alna",20)
```

Cleaner and automatic.

---

## Syntax

```python
class Student:

    def __init__(self):
        print("Object Created")
```

---

## Constructor Example

```python
class Student:

    def __init__(self,name,age):

        self.name=name
        self.age=age

student=Student("Alna",20)

print(student.name)
print(student.age)
```

Output

```
Alna
20
```

---

## Understanding `self`

`self` refers to the **current object**.

Example

```python
self.name
```

means

```
Current object's name
```

Python automatically passes `self`.

---

# Instance Variables

Variables that belong to each object.

Example

```python
class Student:

    def __init__(self,name):

        self.name=name
```

Each object stores its own value.

---

## Example

```python
s1=Student("Alna")
s2=Student("Tom")

print(s1.name)
print(s2.name)
```

Output

```
Alna
Tom
```

---

## Constructor Flow

```
Create Object

↓

__init__()

↓

Store Data

↓

Object Ready
```

---

# 3️⃣ Inheritance

## 📖 What is Inheritance?

Inheritance allows one class to inherit properties and methods from another class.

It helps in **code reusability**.

---

## Parent Class

Also called

- Base Class
- Super Class

---

## Child Class

Also called

- Derived Class
- Sub Class

---

## Syntax

```python
class Parent:
    pass

class Child(Parent):
    pass
```

---

## Example

```python
class Animal:

    def speak(self):
        print("Animal Speaks")

class Dog(Animal):

    pass

dog=Dog()

dog.speak()
```

Output

```
Animal Speaks
```

---

## Child Adding New Method

```python
class Animal:

    def eat(self):
        print("Eating")

class Dog(Animal):

    def bark(self):
        print("Barking")
```

---

## Types of Inheritance

### Single

```
Parent

↓

Child
```

---

### Multilevel

```
Grandparent

↓

Parent

↓

Child
```

---

### Multiple

```
Parent1

   ↘

    Child

   ↗

Parent2
```

---

## Benefits

- Code Reuse
- Less Duplicate Code
- Easy Maintenance
- Better Organization

---

# 4️⃣ Encapsulation

## 📖 What is Encapsulation?

Encapsulation means:

> **Wrapping data and methods together while controlling access to data.**

Real-life example

```
ATM Machine

↓

Cannot directly access money

↓

Must use

Deposit()

Withdraw()
```

---

## Public Variable

```python
self.name
```

Accessible from anywhere.

---

## Private Variable

```python
self.__marks
```

Cannot be accessed directly.

---

## Example

```python
class Student:

    def __init__(self):

        self.__marks=95

    def show(self):

        print(self.__marks)

student=Student()

student.show()
```

Output

```
95
```

---

## Why Encapsulation?

- Protect Data
- Prevent Accidental Changes
- Improve Security
- Better Control

---

# 5️⃣ Polymorphism

## 📖 What is Polymorphism?

Polymorphism means

> **One Interface → Multiple Forms**

Same method name

Different behavior

---

## Example

```python
class Dog:

    def sound(self):
        print("Bark")

class Cat:

    def sound(self):
        print("Meow")

animals=[Dog(),Cat()]

for animal in animals:

    animal.sound()
```

Output

```
Bark

Meow
```

---

## Method Overriding

```python
class Animal:

    def sound(self):
        print("Animal Sound")

class Dog(Animal):

    def sound(self):
        print("Bark")
```

Dog replaces the parent's method.

---

# 6️⃣ Organizing Code Using OOP

Instead of writing everything in one file:

```python
name="Alna"

marks=90

def calculate():
```

Group related data and methods.

```python
class Student:

    def __init__(self,name,marks):

        self.name=name
        self.marks=marks

    def grade(self):

        if self.marks>=90:
            return "A"

        return "B"

student=Student("Alna",92)

print(student.grade())
```

---

## Benefits of OOP Organization

✅ Code is modular

✅ Easy to reuse

✅ Easier debugging

✅ Better readability

✅ Suitable for large projects

---

# 🏛️ Four Pillars of OOP

| Pillar | Purpose |
|---------|---------|
| Class | Blueprint |
| Object | Instance |
| Inheritance | Code Reuse |
| Encapsulation | Data Protection |
| Polymorphism | Multiple Behaviors |

---

# 🌍 Real-World Examples

| Object | Attributes | Methods |
|----------|------------|----------|
| Student | Name, Age | Study(), Write() |
| Car | Brand, Color | Start(), Stop() |
| Mobile | Model, Price | Call(), Charge() |
| Bank Account | Account No, Balance | Deposit(), Withdraw() |

---

# 🎯 Advantages of OOP

- Reusable Code
- Modular Design
- Easier Maintenance
- Better Security
- Scalable Applications
- Easy Collaboration
- Real-world Modeling

---

# ⚠️ Common Mistakes

❌ Forgetting `self`

❌ Accessing private variables directly

❌ Forgetting to create an object

❌ Confusing classes and objects

❌ Not using constructors for initialization

---

# 💼 Interview Questions

### 1. What is OOP?

A programming paradigm that organizes code using classes and objects.

---

### 2. What is a class?

A blueprint for creating objects.

---

### 3. What is an object?

An instance of a class.

---

### 4. What is a constructor?

A special method (`__init__`) that runs automatically when an object is created.

---

### 5. What is `self`?

It refers to the current object.

---

### 6. What is an instance variable?

A variable that belongs to an object.

---

### 7. What is inheritance?

The process of inheriting properties and methods from another class.

---

### 8. What is encapsulation?

Protecting data by controlling access to it.

---

### 9. What is polymorphism?

Using the same method name with different behaviors.

---

### 10. What are the four pillars of OOP?

- Encapsulation
- Inheritance
- Polymorphism
- Abstraction *(advanced concept)*

---

# 📝 Quick Revision

| Concept | Remember |
|----------|----------|
| Class | Blueprint |
| Object | Real Instance |
| Constructor | Initializes Object |
| `self` | Current Object |
| Instance Variable | Object Data |
| Inheritance | Reuse Code |
| Encapsulation | Protect Data |
| Polymorphism | One Method, Many Behaviors |

---

# 🎯 Summary

- A **class** is a blueprint.
- An **object** is created from a class.
- A **constructor (`__init__`)** initializes object data.
- **Instance variables** store data unique to each object.
- **Inheritance** allows one class to reuse another class's features.
- **Encapsulation** protects data by restricting direct access.
- **Polymorphism** lets the same method behave differently for different objects.
- OOP makes programs **modular, reusable, scalable, and easier to maintain**.
