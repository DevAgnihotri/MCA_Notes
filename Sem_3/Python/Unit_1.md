# Introduction to Python Unit 1 Topics

## Table of Contents

- [Introduction to Python: Basics and History](#introduction-to-python-basics)
- [Features and Setting Up Python and Path with working , file execution script vs interactive](#setting-up-python-and-path)
- [Python Data, Variables & Operators](#python-data-variables--operators)
- [id() and type() Functions](#id-and-type-functions)
- [Coding Standards, variable, constants, keyword, identitfier, type conversion and esc seq](#coding-standards)
- [Input-Output in Python](#input-output-in-python)
- [Control Structures in Python](#control-structures-in-python)
- [Iteration Control Structures](#iteration-control-structures)
- [Break, Continue & Pass](#break-continue--pass)
- [Comments](#comments)

## Introduction to Python: Basics

Python is a popular programming language that is easy to read and write. It is used for making websites, games, apps, and more. Python is known for its simple syntax (rules for writing code) and is a great choice for beginners.

### What is Python?

- Python is a high-level (easy to understand) programming language.
- It was created by Guido van Rossum in 1991.
- Python can be used for web development(django), data science(pandas, numpy, matplotlib, seaborn), machine learning(scikitlearn, tensorflow), and more.

**Example:**

```python
print("Hello, World!")
```

This code prints the words Hello, World! on the screen.

Here you go — **History and Versions of Python in 8 simple points** (8th-grade English):

---

### **History and Versions of Python (8 Simple Points)**

1. **Python was created by Guido van Rossum** in 1989 because he wanted an easy and clean programming language.

2. **Python 1.0** was released in 1994 with basic features like functions and modules.

3. **Python 2.0** came in 2000 and added big features like list comprehensions and automatic memory cleanup.

4. **Python 3.0** was released in 2008 to improve the language, but it was _not fully compatible_ with Python 2.

5. **Python 2 officially ended in 2020**, meaning no more updates or support for it.

6. Today we use **Python 3 (3.6 to 3.13 versions)**, which keeps getting faster, cleaner, and more powerful.

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

### **PyCharm vs VS Code vs Jupyter (5-Point Table)**

| Feature        | **PyCharm**                | **VS Code**                  | **Jupyter Notebook**              |
| -------------- | -------------------------- | ---------------------------- | --------------------------------- |
| **Type**       | Full Python IDE            | Multi-language code editor   | Interactive notebook              |
| **Speed**      | Heavy/slow                 | Fast/Light                   | Medium                            |
| **Best Use**   | Large Python projects      | General coding & web dev     | Data science & ML                 |
| **Code Style** | Full scripts, strong tools | Full scripts with extensions | Code in cells with instant output |
| **Debugging**  | Excellent                  | Good                         | Limited                           |

---

### **Features of Python**

#### **1. Interpreted Language**

Python is an **interpreted** language. This means the code is read and run **line by line** by the Python interpreter.
Because of this, you don’t need to “compile” your program before running it.

#### **2. Dynamic Typing**

Python uses **dynamic typing**. This means you **don’t have to tell** the computer what type of data a variable holds.
Example:

```python
x = 5     # integer
x = "Hi"  # now it becomes a string
```

The type changes automatically.

#### **3. Portable (Cross-Platform)**

Python is **portable**, which means the same Python code works on **Windows, Mac, and Linux** without changing anything.
You can write the program once and run it anywhere.

#### **4. Easy Readability**

Python has very **clean and readable** syntax.
It looks like normal English, which makes it easy to understand and learn.
It also uses **indentation** instead of curly brackets `{}` to structure code.

#### **5. Large Standard Library**

Python comes with a **big built-in library**.
You get ready-made modules for things like math, dates, random numbers, web tools, files, etc.
You don’t have to write everything from scratch.

#### **6. Object-Oriented**

Python supports **Object-Oriented Programming (OOP)**.
This helps you create classes, objects, and reusable code.
It makes big programs easier to manage.

#### **7. Extensible & Embeddable**

You can add code from other languages like **C or C++**, or even put Python inside another program.
This makes Python very flexible.

#### **8. High-Level Language**

### **How Python Works (Simple Explanation)**

1. **Python is an interpreted language**, which means the final execution happens **line by line** using the Python Interpreter (PVM).

2. Before running, Python does a **small internal compilation** to convert the `.py` file into **bytecode**.
   This bytecode is NOT machine code — it is just a simpler form for Python to understand.

3. The generated bytecode is stored as a `.pyc` file inside the `__pycache__` folder.

4. The **Python Virtual Machine (PVM)** reads this bytecode and interprets each instruction **line by line**.

5. The result is shown on the screen — this is the final output of the program.

---

#### **Ultra-Short Summary**

Python → compiles to **bytecode** → interpreter (PVM) runs it **line by line** → output.

Here is the **updated table** with the **bytecode difference added** — clean and simple:

---

### **Python File Execution (Updated Table)**

| Feature                  | **Script Mode**                                            | **Interactive Mode**                              |
| ------------------------ | ---------------------------------------------------------- | ------------------------------------------------- |
| **Where Code Runs**      | In a saved `.py` file                                      | Directly in Python shell (`>>>`)                  |
| **Execution Style**      | Runs the whole file at once                                | Runs one line at a time                           |
| **Bytecode Compilation** | Compiles to bytecode **and saves** `.pyc` in `__pycache__` | Compiles to bytecode **but does NOT save** `.pyc` |
| **Best For**             | Full programs, long code                                   | Quick tests, checking small code pieces           |
| **Saving Code**          | Code is saved permanently                                  | Code is not saved automatically                   |

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
![Operators in Python](https://media.geeksforgeeks.org/wp-content/uploads/20240430181610/Operators-in-python.webp)

*Figure: Common operators in Python.*

![Operator Precedenece in Python](https://miro.medium.com/1*WzSiL_jo4yXwBf_nrt5M3A.png)

*Operator precedenece in Python.*
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

Here is a **simple, clean, 8th-grade level explanation** of all the topics:

---

### **Variables and Constants**

* A **variable** is a name that stores a value.
  Example: `x = 10`
* The value of a variable **can change** during the program.
* A **constant** is a value that is **not supposed to change**.
  Python does not have real constants, but by rule we write them in **capital letters**:
  Example: `PI = 3.14`

### **Keywords**

* Keywords are **special reserved words** in Python.
* They have a fixed meaning and **cannot be used as variable names**.
  Examples: `if`, `while`, `for`, `True`, `False`, `class`, `return`

### **Identifiers**

* Identifiers are the **names** given to variables, functions, classes, etc.
* Rules:

  * Can contain letters, digits, underscore
  * Cannot start with a digit
  * Cannot be a keyword
  * No spaces allowed
    Example: `my_value`, `student1`, `total_sum`

---

### **Type Conversion**

Python can change one data type to another.

#### **1. Implicit Type Conversion**

* Python **automatically** converts data from one type to another.
* Happens when two different types are used in a calculation.
  Example:

  ```python
  x = 5       # int
  y = 2.5     # float
  z = x + y   # Python converts int → float
  ```

#### **2. Explicit Type Conversion**

* The programmer **manually** converts the type.
* Uses functions like `int()`, `float()`, `str()`.
  Example:

  ```python
  x = "10"
  y = int(x)   # string → int
  ```

---

### **Escape Sequences**

Escape sequences are **special characters** used inside strings to format text.

| Escape Sequence | Meaning         | Example            |
| --------------- | --------------- | ------------------ |
| `\n`            | New line        | `"Hello\nWorld"`   |
| `\t`            | Tab (big space) | `"Name:\tDev"`     |
| `\\`            | Backslash       | `"C:\\folder"`     |
| `\'`            | Single quote    | `'It\'s nice'`     |
| `\"`            | Double quote    | `"He said \"Hi\""` |

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

## Comments

Comments are notes you write **inside the code** to explain what it does.
Python **ignores** comments when running the program.

---

### **1. Single-line Comment → `#`**

* Used for short notes.
* Everything after `#` is ignored.

#### Example:

```python
# This adds two numbers
x = 5 + 3
```

---

### **2. Multi-line Comment → `"""  """` or `'''  '''`**

* Used when you want to write **many lines** of explanation.
* Python ignores the text inside these quotes.

#### Example:

```python
"""
This program shows
how multi-line comments work.
"""
```

---

### **3. Docstring (Documentation String)**

* A docstring is a special multi-line string placed at the **start of a function, class, or file**.
* It explains **what the function does**.
* Can be accessed using `function.__doc__`.

#### Example:

```python
def add(a, b):
    """This function adds two numbers."""
    return a + b
```

---

# **Python Keywords — Use & Syntax Table**

| **Keyword**      | **Use**                     | **Syntax / Example**    |
| ---------------- | --------------------------- | ----------------------- |
| **False / True** | Boolean values              | `x = True`              |
| **None**         | No value / empty            | `x = None`              |
| **and**          | Logical AND                 | `a and b`               |
| **or**           | Logical OR                  | `a or b`                |
| **not**          | Logical NOT                 | `not a`                 |
| **if**           | Condition                   | `if x > 5:`             |
| **elif**         | Else-if condition           | `elif x == 5:`          |
| **else**         | Default condition           | `else:`                 |
| **for**          | Loop                        | `for i in range(5):`    |
| **while**        | Loop                        | `while x < 10:`         |
| **break**        | Stop loop                   | `break`                 |
| **continue**     | Skip to next loop step      | `continue`              |
| **pass**         | Empty statement             | `pass`                  |
| **def**          | Define function             | `def hello():`          |
| **return**       | Return value from function  | `return x`              |
| **class**        | Create class                | `class Car:`            |
| **try**          | Try block                   | `try:`                  |
| **except**       | Handle errors               | `except ValueError:`    |
| **finally**      | Runs always                 | `finally:`              |
| **raise**        | Raise an error              | `raise ValueError()`    |
| **with**         | Managed block               | `with open(...) as f:`  |
| **import**       | Import module               | `import math`           |
| **from**         | Import parts of module      | `from math import sqrt` |
| **as**           | Rename module               | `import math as m`      |
| **global**       | Declare global variable     | `global x`              |
| **nonlocal**     | Use outer function variable | `nonlocal count`        |
| **lambda**       | Small anonymous function    | `lambda x: x+1`         |
| **is**           | Identity check              | `a is b`                |
| **in**           | Membership check            | `if x in list:`         |
| **assert**       | Debug check                 | `assert x > 0`          |
| **del**          | Delete variable             | `del x`                 |
| **async**        | Async function              | `async def func():`     |
| **await**        | Wait for async task         | `await work()`          |
| **yield**        | Return generator value      | `yield x`               |

---
