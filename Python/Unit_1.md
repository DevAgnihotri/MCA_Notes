# Introduction to Python Unit 1 Topics

This section covers the basics of Python programming, including how to get started, set up Python on your computer, and understand the main building blocks of the language. You will learn about Python data types, variables, and operators, as well as important built-in functions like id() and type(). Finally, you will discover coding standards that help you write clean and readable Python code. These notes are designed to be simple and easy to understand, with clear definitions, examples, and explanations for beginners.

## Table of Contents

- [Introduction to Python: Basics](#introduction-to-python-basics)
- [Setting Up Python and Path](#setting-up-python-and-path)
- [Python Data, Variables & Operators](#python-data-variables--operators)
- [id() and type() Functions](#id-and-type-functions)
- [Coding Standards](#coding-standards)
- [Input-Output in Python](#input-output-in-python)
- [Control Structures in Python](#control-structures-in-python)
- [Iteration Control Structures](#iteration-control-structures)
- [Break, Continue & Pass](#break-continue--pass)

## Introduction to Python: Basics

Python is a popular programming language that is easy to read and write. It is used for making websites, games, apps, and more. Python is known for its simple syntax (rules for writing code) and is a great choice for beginners.

### What is Python?

- Python is a high-level (easy to understand) programming language.
- It was created by Guido van Rossum in 1991.
- Python can be used for web development, data science, automation, and more.

**Example:**

```python
print("Hello, World!")
```

This code prints the words Hello, World! on the screen.

---

## Setting Up Python and Path

To use Python, you need to install it on your computer.

- Download Python from the official website: https://python.org
- Install it by following the instructions.

**Setting up Path:**

- The "path" is a list of folders where your computer looks for programs.
- Adding Python to the path lets you run Python from any folder using the command prompt.
- During installation, check the box "Add Python to PATH".

**How to check Python installation:**

- Open Command Prompt and type:

```
python --version
```

If Python is installed, you will see the version number.

---

## Python Data, Variables & Operators

### Data in Python

- Data means information that you use in your program, like numbers, words, or lists.
- Python has different types of data:
  - **int:** Whole numbers (e.g., 5, -3)
  - **float:** Decimal numbers (e.g., 3.14, -0.5)
  - **str:** Text or string (e.g., "hello")
  - **bool:** True or False values
  - **list:** A group of items (e.g., [1, 2, 3])
  - **dict:** Key-value pairs (e.g., {"name": "Sam"})

### Variables

- A variable is a name that stores data.
- You can change the value of a variable anytime.

**Example:**

```python
age = 12
name = "Sam"
```

Here, `age` is a variable storing the number 12, and `name` stores the word "Sam".

### Operators

- Operators are symbols that do actions on data.
- Common operators:
  - **+** (plus): Adds numbers or joins strings
  - **-** (minus): Subtracts numbers
  - **\*** (multiply): Multiplies numbers
  - **/** (divide): Divides numbers
  - **%** (modulo): Finds the remainder
  - **==** (equals): Checks if two values are the same
  - **!=** (not equals): Checks if values are different

**Example:**

```python
x = 5 + 3   # x is 8
is_equal = (x == 8)  # is_equal is True
```

---

## id() and type() Functions

- **id() function:** Shows the unique address of a variable in memory.

  - Example:

  ```python
  a = 10
  print(id(a))
  ```

  This prints a number showing where `a` is stored.

- **type() function:** Tells you the type of data stored in a variable.
  - Example:
  ```python
  b = "hello"
  print(type(b))
  ```
  This prints `<class 'str'>` because `b` is a string.

---

## Coding Standards

Coding standards are rules to help you write clean and easy-to-read code.

- Use clear names for variables (e.g., `score`, `user_name`)
- Write comments to explain your code
  - Example:
  ```python
  # This is a comment
  print("Hello!")
  ```
- Use spaces and indentation (tabs or spaces) to organize code
  - Example:
  ```python
  if age > 10:
      print("Older than 10")
  ```
- Follow the PEP 8 style guide for Python
  - PEP 8 is a set of rules for writing Python code

---

## Input-Output in Python

Input and output (I/O) are ways for your program to talk to the user. You can show messages on the screen (output) and get information from the user (input).

### Printing on Screen (OUTPUT)

- Use the `print()` function to show text or numbers on the screen.
- You can print words, numbers, or even the result of calculations.

**Example:**

```python
print("Hello, World!")
print(5 + 3)
```

This will show:

```
Hello, World!
8
```

### Reading Data from Keyboard (INPUT)

- Use the `input()` function to get information from the user.
- The input is always taken as a string (text).

**Example:**

```python
name = input("Enter your name: ")
print("Hello, " + name)
```

If you want a number, you need to change the input to an integer using `int()`:

```python
age = int(input("Enter your age: "))
print("You are", age, "years old.")
```

---

## Control Structures in Python

Control structures help you make decisions and repeat actions in your program.

### if-else Statement

- Used to check if something is true or false and do different things.

**Syntax:**

```python
if condition:
    # code if condition is true
else:
    # code if condition is false
```

**Example:**

```python
age = 15
if age >= 18:
    print("You are an adult.")
else:
    print("You are not an adult.")
```

### elif Statement

- Used when you have more than two choices.

**Syntax:**

```python
if condition1:
    # code if condition1 is true
elif condition2:
    # code if condition2 is true
else:
    # code if none are true
```

**Example:**

```python
marks = 85
if marks >= 90:
    print("Grade: A")
elif marks >= 80:
    print("Grade: B")
else:
    print("Grade: C")
```

### Nested if

- You can put one if statement inside another.

**Example:**

```python
num = 10
if num > 0:
    print("Positive number")
    if num % 2 == 0:
        print("Even number")
else:
    print("Not a positive number")
```

---

## Iteration Control Structures

Iteration means repeating actions. Python has loops for this.

### for Loop

- Used to repeat actions a certain number of times.

**Syntax:**

```python
for variable in sequence:
    # code to repeat
```

**Example:**

```python
for i in range(5):
    print(i)
```

This prints numbers from 0 to 4.

### while Loop

- Used to repeat actions as long as a condition is true.

**Syntax:**

```python
while condition:
    # code to repeat
```

**Example:**

```python
count = 1
while count <= 5:
    print(count)
    count += 1
```

This prints numbers from 1 to 5.

---

## Break, Continue & Pass

### break Statement

- Used to stop a loop early.

**Example:**

```python
for i in range(10):
    if i == 5:
        break
    print(i)
```

This prints numbers 0 to 4 and then stops.

### continue Statement

- Used to skip the rest of the code in the loop for the current step.

**Example:**

```python
for i in range(5):
    if i == 2:
        continue
    print(i)
```

This prints 0, 1, 3, 4 (skips 2).

### pass Statement

- Used as a placeholder when you do not want to write any code yet.

**Example:**

```python
for i in range(3):
    pass  # does nothing
print("Loop finished")
```

---
