# Year 2025

## SECTION A — brief answers (2 × 7 = 14 marks)

### **a. How to handle exceptions in Python**

#### **Definition**

Exception handling is a way to **catch errors** during program execution and **prevent the program from crashing**.

#### **Key Points**

* Done using **try–except** block
* Put risky code inside `try`
* Handle error in `except`
* You can add `else` (runs when no error)
* `finally` always runs (cleanup code)

#### **Syntax**

```python
try:
    # code that may cause error
except ErrorType:
    # code to handle error
```

#### **Example (with def function)**

```python
def divide(a, b):
    try:
        result = a / b
        return result
    except ZeroDivisionError:
        return "Cannot divide by zero!"
    except Exception as e:
        return "Some other error occurred: " + str(e)

print(divide(10, 2))   # 5.0
print(divide(10, 0))   # Cannot divide by zero!
```

---

## **b. Output of the given programs**

### **Function**

```python
def compute(x):
    return [i**2 for i in x if i % 2 == 0]
```

### **Explanation**

* The comprehension keeps **even numbers only**
* Then returns their **squares**
* Input type (tuple or list) does NOT change the result

---

### **1. Input as tuple**

```python
print(compute((1, 2, 3, 4, 5)))
```

Even numbers → 2, 4
Squares → 4, 16

### **Output**

```
[4, 16]
```

---

### **2. Input as list**

```python
print(compute([1, 2, 3, 4, 5]))
```

### **Output**

```
[4, 16]
```

**Both programs give the same output.**

---

## **c. Explain floor division with example**

### **Definition**

Floor division `//` divides two numbers and **rounds the result down** to the nearest whole number.

### **Key Points**

* Symbol: `//`
* Always **rounds down** (towards negative infinity)
* Works for integers and floats

### **Example (with def)**

```python
def floor_example(a, b):
    return a // b

print(floor_example(7, 2))   # 3
print(floor_example(-7, 2))  # -4 (because -3.5 floors to -4)
```

---

## **d. Purpose of the `with` statement in file handling**

### **Definition**

`with` is used to **automatically manage resources** like files.
It **opens** a file and **closes it automatically**, even if an error happens.

### **Key Points**

* Automatically closes the file
* Prevents memory leaks
* Cleaner than manual `file.close()`
* Uses **context manager** internally

### **Syntax**

```python
with open("filename", "mode") as file:
    # work with file
```

### **Example (with def)**

```python
def read_file():
    with open("data.txt", "r") as f:
        content = f.read()
        return content
```

---

### **e. Use of lambda functions in Python**

#### **Definition**

A lambda function is a **small anonymous (nameless) function** used for small tasks.

#### **Key Points**

* Defined using `lambda`
* Used for short, one-line functions
* Common in `map()`, `filter()`, `sorted()`
* No `def` or function name needed

### **Syntax**

```python
lambda arguments: expression
```

### **Example (with def comparison)**

```python
# normal function
def square(x):
    return x * x

# lambda function
sq = lambda x: x * x

print(square(4))  # 16
print(sq(4))      # 16
```

---

### **OR — Assign a single value to a tuple**

### **Rule**

A single-value tuple must have a **comma**.

### **Example**

```python
t = (5,)
print(t)       # (5,)
print(type(t)) # tuple
```

---

## **f. Why NumPy is used instead of Python arrays (lists)**

### **Key Points (Very Important for Exams)**

1. **Faster execution**

   * NumPy uses C and vectorization (no Python loops)

2. **Less memory usage**

   * Stores data in continuous blocks of memory

3. **Supports mathematical operations directly**

   * Vector & matrix operations, linear algebra, etc.

4. **Broadcasting**

   * Allows operations on arrays of different shapes

5. **Works with scientific libraries**

   * SciPy, pandas, scikit-learn, TensorFlow depend on NumPy

### **Example (with def)**

```python
import numpy as np

def numpy_example():
    arr = np.array([1, 2, 3, 4])
    return arr * arr   # element-wise square

print(numpy_example())   # [ 1  4  9 16 ]
```

### **Why lists are weaker**

* No direct math operations (must use loops)
* Slower because loops run in Python
* No multi-dimensional support like NumPy arrays

---

## SECTION B — (7 marks each). I’ll answer all (even though exam asks any three). Each answer contains explanation and a working code sample or clear steps.

### a. Design a basic calculator supporting +, −, ×, ÷ (Python program)

**Explanation:** Provide a simple CLI calculator handling four operations and invalid inputs, also handle division by zero.

**Code (readable, exam-style):**

```python
def add(a, b): return a + b
def sub(a, b): return a - b
def mul(a, b): return a * b
def div(a, b):
    if b == 0:
        raise ZeroDivisionError("Division by zero")
    return a / b

def calculator():
    print("Enter first number:")
    x = float(input().strip())
    print("Enter operation (+, -, *, /):")
    op = input().strip()
    print("Enter second number:")
    y = float(input().strip())
    if op == "+":
        print("Result:", add(x, y))
    elif op == "-":
        print("Result:", sub(x, y))
    elif op == "*":
        print("Result:", mul(x, y))
    elif op == "/":
        try:
            print("Result:", div(x, y))
        except ZeroDivisionError:
            print("Error: Cannot divide by zero.")
    else:
        print("Unknown operation.")

if __name__ == "__main__":
    calculator()
```

**Notes:** Could be extended with loops, support for more operations, GUI, or expression parsing (using `eval` cautiously).

---

### b. Membership and Identity operators; difference between `a is b` and `a == b`

**Membership operators:**

* `in` — True if an element is present in a container (`x in list`).
* `not in` — True if the element is not present.

**Identity operators:**

* `is` — True if two references point to the exact same object (same memory).
* `is not` — True if they are different objects.

**Given:**

```python
a = 3
b = 3
```

**`a == b`** checks **value equality**: Are the values equal? → `True`.
**`a is b`** checks **identity**: Do `a` and `b` refer to the same object? For small integers, CPython caches small integers so `a is b` is usually `True` for `3`. But identity is not the same as equality in general.

**Example where equality holds but identity does not:**

```python
x = [1,2]
y = [1,2]
x == y    # True (same contents)
x is y    # False (different objects in memory)
```

**Key point:** Use `==` to compare values; use `is` only to check identity (e.g., `if var is None:`).

---

### c. Function to count frequency of each character in a string

**Approach:** Use a dictionary to count characters, or `collections.Counter` for brevity.

**Code (dictionary-based):**

```python
a= input("Enter the string")
freq = {}

for ch in a:
    freq[ch] = freq.get(ch,0) + 1

print(freq)
```

---

### d. Program to reverse the contents of a file by reading it character by character

**Approach:** Read whole file content and reverse; reading character by character and writing in reverse order requires storing characters (or using seek to read from end). Simpler: read content, reverse string, write to another file.

**Code (simple and reliable):**

```python
with open("file.txt","r",encoding='utf-8') as fin:
    content = fin.read()

rev_content = content[::-1]

with open("new.txt","w",encoding='utf=8') as fout:
    fout.write(rev_content)

```

---


## SECTION C — (Attempt any one) — I’ll answer both options.

### C(a). Short notes with examples — Operator Precedence, Python Indentation, Type Conversion

**1. Operator Precedence**

* **Definition:** Order in which Python evaluates operators in an expression. Parentheses `()` have highest precedence, then exponentiation `**`, then unary `+ -`, multiplication/division `*, /, //, %`, addition/subtraction `+ -`, comparison, logical operators (`not`, `and`, `or`) and so on.
* **Example:** `2 + 3 * 4` → `2 + (3*4)` = `14`, not `(2+3) * 4`. Use parentheses to force desired order.

**2. Python Indentation**

* **Definition:** Python uses indentation (whitespace at beginning of a line) to define blocks of code instead of braces. Correct indentation is required; inconsistent use of tabs/spaces raises `IndentationError`.
* **Example:**

  ```python
  if x > 0:
      print("Positive")
      x -= 1
  else:
      print("Non-positive")
  ```
* **Note:** PEP8 recommends 4 spaces per indent level.

**3. Type Conversion (Casting)**

* **Definition:** Converting values from one data type to another using functions like `int()`, `float()`, `str()`, `list()`, `tuple()`, etc. Python performs implicit conversion sometimes (e.g., int to float in mixed arithmetic), but explicit conversion is safer.
* **Example:**

  ```python
  s = "123"
  n = int(s)      # -> 123
  f = float("3.14")  # -> 3.14
  ```
* **Key point:** Be careful with invalid conversions (e.g., `int("abc")` raises `ValueError`).

---

### C(b). Program to validate email addresses using regular expressions

**Criteria:** Must contain `@`, must contain a domain name, should not contain spaces.

**Solution approach:** Use `re` with a pattern that enforces allowed characters, `@`, domain, and top-level domain. For exam-level validation a simple regex is fine.

**Code:**

```python
import re

pattern = re.compile(r'^[A-Za-z0-9.-_%+]+@[A-Za-z0-9.-]+\.[A-Za-z]{2,}$')

email = input("Enter your mail")
if ' ' in email:
    print("Wrong")
elif bool(pattern.match(email)):
    print("it's ok")
else:
    print("Wrong dear")
```

**Explanation:**

* `^[A-Za-z0-9._%+-]+` — local part (allowed chars).
* `@` — required symbol.
* `[A-Za-z0-9.-]+` — domain name.
* `\.[A-Za-z]{2,}$` — top-level domain (e.g., `.com`, `.in`) of at least 2 letters.
  **Note:** Real email validation can be more complex; this regex covers common valid forms and forbids spaces.

---

## SECTION D — (Attempt any one) — I'll answer all three options requested (a, b, c).

### D(a). Why loops are used in Python. Types of loops. `break` and `continue` with examples.

**Why loops:** Loops let us repeat a block of code multiple times, useful for iterating over collections, performing repeated calculations, processing files line-by-line, etc.

**Types of loops in Python:**

1. **`for` loop** — iterates over items of a sequence or any iterable.

   ```python
   for i in [1,2,3]:
       print(i)
   ```
2. **`while` loop** — repeats as long as a condition is true.

   ```python
   while x > 0:
       x -= 1
   ```

**`break`:** Immediately exits the loop.

```python
for n in range(1, 10):
    if n == 5:
        break  # loop stops when n==5
    print(n)
# prints 1,2,3,4
```

**`continue`:** Skips to the next iteration, continuing the loop.

```python
for n in range(1, 6):
    if n % 2 == 0:
        continue
    print(n)
# prints 1,3,5
```

**Key points:** Use `break` to stop early (e.g., when found), `continue` to skip unwanted iterations. Both work in `for` and `while`.

---

### D(b). Function to find the longest word in a list

**Code and explanation:**

```python
def longest_word(words):
    if not words:
        return None  # or ""
    longest = max(words, key=len)
    return longest

print(longest_word(['apple', 'banana', 'cherry']))  # -> 'banana'
```

or

```python
a = ["longest","medium_","small"]
length = 0
for word in a:
    if len(word) > length:
        max_w = word
        length = len(word)

print(max_w)
```


**Alternative**

```python
a = ["longest", "medium_", "small"]

max_w = max(a, key=len)
print(max_w)
```

**Notes:** `max(..., key=len)` is pythonic and O(n) time.

---

### D(c). Distinguish between a tuple and a list with examples. Also explain at least 4 built-in dictionary methods.

**Tuple vs List:**

1. **Mutability:**

   * List (`[]`) is mutable — can change, add, remove elements.
   * Tuple (`()`) is immutable — cannot change after creation.
2. **Syntax:**

   * List: `lst = [1, 2, 3]`
   * Tuple: `t = (1, 2, 3)` or single-element tuple: `(5,)`
3. **Use-cases:**

   * Use tuples for fixed collections (like coordinates), keys in dictionaries (if immutable), or return multiple values.
   * Use lists for collections that change, need sorting, append/pop, etc.
4. **Performance:** Tuples can be slightly faster and use less memory due to immutability.

**Examples:**

```python
lst = [1, 2]
lst.append(3)   # OK

t = (1, 2)
# t.append(3) -> AttributeError (tuples have no append)
```

**Four built-in dictionary methods (with explanation):**

1. `dict.keys()` — returns a view of keys.

   ```python
   d = {'a':1, 'b':2}
   list(d.keys())  # -> ['a', 'b']
   ```
2. `dict.values()` — returns a view of values.

   ```python
   list(d.values())  # -> [1, 2]
   ```
3. `dict.items()` — returns (key, value) pairs view. Useful for iteration.

   ```python
   for k, v in d.items():
       print(k, v)
   ```
4. `dict.get(key, default=None)` — safe retrieval; returns `default` if key missing (no KeyError).

   ```python
   d.get('c', 0)  # -> 0
   ```

(Additional useful methods: `update()`, `pop()`, `popitem()`, `clear()`, `setdefault()`.)

---

## SECTION E — (Attempt any one)

### E(a). Different types of file modes in Python with examples

**Common file modes (with meaning and example):**

1. `'r'` — read (default). File must exist.

   ```python
   with open("file.txt", "r") as f:
       data = f.read()
   ```
2. `'w'` — write (truncate file or create if not exists).

   ```python
   with open("out.txt", "w") as f:
       f.write("Hello")
   ```
3. `'a'` — append (write at end, create if not exists).

   ```python
   with open("log.txt", "a") as f:
       f.write("New line\n")
   ```
4. `'x'` — create and open for writing; fails if file exists (useful to avoid overwrite).

   ```python
   with open("newfile.txt", "x") as f:
       f.write("Created")
   ```
5. `'b'` — binary mode (combine with others, e.g., `'rb'`, `'wb'`) for non-text files.

   ```python
   with open("image.jpg", "rb") as f:
       data = f.read()
   ```
6. `'t'` — text mode (default). `'rt'` same as `'r'`.
7. `'+'` — update mode (read and write). Examples: `'r+'` (read/write, file must exist), `'w+'` (write/read, truncates or creates).

**Examples combining modes:**

* `'rb'` — read binary.
* `'w+'` — open for writing and reading; truncates existing file or creates new.

---

### E(b). Program to read a CSV file and display rows where a specific column value exceeds a threshold

**Assume CSV has header, e.g., `name,score` and we want rows where `score > threshold`.**

**Code using csv module (works in standard library):**

```python
import pandas as pd
df = pd.read_csv("students.csv")
print(df[df['score'] > 75])
```

---

## SECTION F — (Attempt any one)

### F(a). Role of event handling in Tkinter; how to bind events to widgets (with examples)

**Role of event handling:** Event handling allows GUI programs to respond to user actions (mouse clicks, key presses, window events). Widgets generate events; you bind handlers (callback functions) to respond.

**Binding events:**

* Use widget methods like `widget.bind(event, handler)` where `event` is a string like `"<Button-1>"` for left mouse click, `"<Key>"` for key press, etc.
* For buttons, commonly use `command=` parameter for click handlers.

**Examples:**

```python
import tkinter as tk

def on_click(event):
    print("Clicked at", event.x, event.y)

def on_key(event):
    print("Pressed", event.keysym)

root = tk.Tk()
label = tk.Label(root, text="Click me or press a key")
label.pack(padx=20, pady=20)

# Bind left mouse click to label
label.bind("<Button-1>", on_click)

# Bind any key press on root window
root.bind("<Key>", on_key)

# Button with command
def say_hello():
    print("Hello!")

btn = tk.Button(root, text="Say Hello", command=say_hello)
btn.pack()

root.mainloop()
```

**Key points:**

* `event` object has attributes like `x`, `y`, `keysym`, `char`.
* Use `bind` for general events; use `command` for simple button callbacks.
* You can bind to widget-level or root-level (global) events. Use `unbind` to remove a binding.

---

### F(b). Program to read `students.csv`, calculate average marks for each student, and display results

**Assume `students.csv` has rows like: `name,mark1,mark2,mark3` or `name,subject,marks` — I'll assume per-student multiple mark columns (common case).**

**Code assuming `name, m1, m2, m3, ...`:**

**If CSV is long or has varying columns, consider `pandas`:**

```python
import pandas as pd
df = pd.read_csv("students.csv")
# assume first column 'name' or 'roll_no', rest are marks
# Take all columns from index 2 to the end
df['Average'] = df.iloc[:, 1:].mean(axis=1)
print(df[['name', 'Average']])
```


# Year 2023

Sure love ❤️ I’ll answer **everything in simple, easy, learnable English** with **definitions, points, syntax, and examples**.
Answers are fully exam-oriented and according to **marks**.

---

# ✅ **SECTION A — Short Answers**

---

## **1. Define the programming cycle for Python.**

**Definition:**
The programming cycle is the series of steps followed to write, run, test, and maintain Python programs.

### **Steps in Python Programming Cycle**

1. **Editing / Writing Code**

   * We write the Python program using an editor or IDE.

2. **Saving the Program**

   * Save with `.py` extension.

3. **Execution / Running**

   * Python interpreter reads the file line-by-line and executes it.

4. **Testing / Debugging**

   * Errors are found and corrected.

5. **Maintenance**

   * Code is updated or improved when required.

---

## **2. Describe the use of class `__init__()` method.**

**Definition:**
`__init__()` is a **constructor method** that automatically runs when an object is created.

### **Purpose**

* To **initialize variables** of a class.
* To set default or starting values.

### **Syntax**

```python
class MyClass:
    def __init__(self, x, y):
        self.x = x
        self.y = y
```

### **Example**

```python
obj = MyClass(10, 20)
```

---

## **3. Explain features of any two Python IDEs.**

### **(a) PyCharm**

* Smart code completion
* Bug/error detection
* Powerful debugger
* Project management support

### **(b) Jupyter Notebook**

* Runs code in cells
* Great for data science
* Shows output instantly
* Supports plots, charts, Markdown notes

---

## **4. Purpose of `break` and `continue` in loops.**

### **break**

* Stops the loop immediately.

```python
for i in range(5):
    if i == 3:
        break
```

### **continue**

* Skips the current iteration and moves to next.

```python
for i in range(5):
    if i == 3:
        continue
```

---

## **5. Explain mutable sequences in Python.**

**Definition:**
Mutable sequences are data structures whose elements **can be changed after creation**.

### **Examples**

* List
* Dictionary
* Set

```python
lst = [1,2,3]
lst[1] = 10  # valid (mutable)
```

---

## **6. Explain the output of:**

```python
def printalpha(abc_list, num_list):
    for char in abc_list:
        for num in num_list:
            print(char, num)
    return

printalpha(['a', 'b', 'c'], [1, 4, 1])
```

### **Explanation**

This is a **nested loop**.
For every letter in `abc_list`, all numbers in `num_list` are printed.

### **Output**

```
a 1
a 4
a 1
b 1
b 4
b 1
c 1
c 4
c 1
```

---

## **7. Discuss special methods `__len__` and `__ne__`.**

### **`__len__()`**

* Returns length of an object.
* Called when `len(obj)` is used.

```python
def __len__(self):
    return self.size
```

### **`__ne__()`**

* Stands for “not equal”.
* Called when `!=` operator is used.

```python
def __ne__(self, other):
    return self.value != other.value
```

---

## **8. Various file opening modes in Python.**

| Mode | Meaning                 |
| ---- | ----------------------- |
| `r`  | Read only               |
| `w`  | Write (overwrites file) |
| `a`  | Append (adds at end)    |
| `r+` | Read + write            |
| `b`  | Binary mode             |
| `t`  | Text mode               |

Example:

```python
f = open("data.txt", "w")
```

---

## **9. Compare `assert`, `try-except`, and `raise`.**

### **assert**

* Used for testing conditions.

```python
assert x > 0
```

### **try-except**

* Used to handle runtime errors.

```python
try:
    x = 5/0
except:
    print("Error!")
```

### **raise**

* Used to throw an error manually.

```python
raise ValueError("Wrong input")
```

---

## **10. Python function for linear search**

```python
def linear_search(arr, key):
    for i in range(len(arr)):
        if arr[i] == key:
            return i
    return -1
```

---

# ✅ **SECTION B — Attempt Any 3 (Long Answers)**

---

## **1. Fibonacci series using recursion**

```python
def fib(n):
    if n <= 1:
        return n
    else:
        return fib(n-1) + fib(n-2)

# display n terms
n = 6
for i in range(n):
    print(fib(i))
```

---

## **2. Algorithm + Python code to generate prime numbers**

### **Algorithm**

1. Take range limit.
2. Check each number from 2 to limit.
3. For each number, check divisibility.
4. If divisible only by 1 and itself → prime.

### **Code**

```python
def primes(n):
    for num in range(2, n+1):
        for i in range(2, num):
            if num % i == 0:
                break
        else:
            print(num)
```

---

## **3. Compare list vs tuple + list comprehension**


### **List**

* Mutable
* Can change elements

```python
lst = [1,2,3]
```

### **Tuple**

* Immutable
* Faster

```python
t = (1,2,3)
```

### **List Comprehension**

Short way to create lists.

```python
squares = [x*x for x in range(5)]
```

---


### **Code**

```python
def selection_sort(arr):
    for i in range(len(arr)):
        min_i = i
        for j in range(i+1, len(arr)):
            if arr[j] < arr[min_i]:
                min_i = j
        arr[i], arr[min_i] = arr[min_i], arr[i]
    return arr

data = [2,5,2,1,5,2,54,62,4]
print(selection_sort(data))
```

### **Final Sorted Output**

```
[1, 2, 2, 2, 4, 5, 5, 54, 62]
```

Got you Dev ❤️🔥
I’ll continue from **SECTION C onward**, with **full detailed, simple-English, exam-ready answers**.

---

# ✅ **SECTION C — Attempt ANY ONE (10 marks)**

---

# **Q1(a) Discuss various categories of operators in Python.**

Python operators are symbols used to perform operations on variables and values.

### **1. Arithmetic Operators**

Used for mathematical operations.

* `+` (addition)
* `-` (subtraction)
* `*` (multiplication)
* `/` (division)
* `//` (floor division)
* `%` (modulus)
* `**` (power)

### **2. Relational / Comparison Operators**

Used to compare two values.

* `==`, `!=`, `>`, `<`, `>=`, `<=`

### **3. Logical Operators**

Used to combine conditions.

* `and`, `or`, `not`

### **4. Bitwise Operators**

Work on bits (0 and 1).

* `&` (AND)
* `|` (OR)
* `^` (XOR)
* `<<` (left shift)
* `>>` (right shift)

### **5. Assignment Operators**

Used to assign values.

* `=`, `+=`, `-=`, `*=`, `/=`, `%=`, `//=`, `**=`

### **6. Membership Operators**

Check membership.

* `in`, `not in`

### **7. Identity Operators**

Check memory location.

* `is`, `is not`

---

## **Now the expressions (step-wise):**

Given: **a = 3, b = 5, c = 10**

---

### **i) `a & b << b / 5 ** 2 + c * b`**

Let’s break into steps:

### **Step 1: Power**

`5 ** 2 = 25`

### **Step 2: Division**

`b / 25 = 5 / 25 = 0.2`

### **Step 3: Multiplication**

`c * b = 10 * 5 = 50`

### **Step 4: Addition**

`0.2 + 50 = 50.2`

### **Step 5: Bitwise shift**

`b << 50.2`
Shift requires **integer**, so Python ERROR
➡️ **Expression is invalid** because bitwise shift doesn’t accept float.

**Final:** Expression leads to **TypeError**.

---

### **ii) `b >> a ** 2 << 2 >> b ** 2 + c ** 3`**

Given:
`a = 3`, `b = 5`, `c = 10`

### **Step 1: Powers**

`a ** 2 = 9`
`b ** 2 = 25`
`c ** 3 = 1000`

### **Step 2: Addition**

`25 + 1000 = 1025`

### **Step 3: Evaluate bitwise**

`5 >> 9 << 2 >> 1025`

* `5 >> 9` → shifting right more than bit size ⇒ **0**
* `0 << 2` = 0
* `0 >> 1025` = 0

### ✔️ Final Answer: **0**

---

# **Q1(b) HISTORY AND FEATURES OF PYTHON**

### **History**

* Created by **Guido van Rossum** in **1991**.
* Inspired by ABC language.
* Named after “Monty Python”.
* Gained huge popularity in AI, ML, web development, data science.
* Python 2 released in 2000.
* Python 3 released in 2008.

---

## **FEATURES**

1. **Easy and simple syntax**
2. **Interpreted language** (runs line-by-line)
3. **Platform independent**
4. **Large standard library**
5. **Supports OOP and procedural both**
6. **Huge community support**
7. **Automatic memory management (Garbage Collection)**
8. **Extensible** (C, Java modules)

---

## **Why Python is an interpreted language?**

* Python code is executed **line by line**.
* The interpreter reads one line → converts to bytecode → executes.
* No separate compile step.

---

## **Python 2 vs Python 3**

| Python 2                        | Python 3               |
| ------------------------------- | ---------------------- |
| Deprecated                      | Actively used          |
| `print "Hello"`                 | `print("Hello")`       |
| `/` gives integer in some cases | `/` always gives float |
| Slower                          | Faster                 |
| No Unicode by default           | Unicode strings        |

---

# ✅ **SECTION 2 — Attempt ANY ONE (10 marks)**

---

## **Q2(a) Program to count vowels in a string**

### **Vowels:** a, e, i, o, u (both upper and lower)

### **Code**

```python
def count_vowels(text):
    vowels = "aeiouAEIOU"
    count = 0
    for ch in text:
        if ch in vowels:
            count += 1
    return count

# Example
s = "Hello World"
print("Vowels:", count_vowels(s))
```

### **Output explanation**

Input: **"Hello World"**

Vowels → e, o, o
Count = **3**

---

## **Q2(b) Capitalize all lines**

```python
lines = []
print("Enter lines (blank line to stop):")

while True:
    text = input()
    if text == "":
        break
    lines.append(text.upper())

print("\nOutput:")
for line in lines:
    print(line)
```

---

# ✅ **SECTION 3 — Attempt ANY ONE (10 marks)**

---

# **Q3(a) LIST DATA STRUCTURE + METHODS**

### **Definition:**

A **list** is an ordered, mutable sequence in Python.

Example:

```python
numbers = [10, 20, 30]
```

---

## **Important List Methods**

### **1. append()**

Adds item at end.

```python
lst.append(5)
```

### **2. insert()**

Adds item at index.

```python
lst.insert(1, 100)
```

### **3. remove()**

Removes first occurrence.

```python
lst.remove(20)
```

### **4. pop()**

Removes and returns element.

```python
item = lst.pop()
```

### **5. sort()**

Sort list.

```python
lst.sort()
```

### **6. reverse()**

Reverse list.

```python
lst.reverse()
```

### **7. extend()**

Adds all items from another list.

```python
lst.extend([7, 8])
```

---

# **Q3(b) LIST vs DICTIONARY**

| List                        | Dictionary                  |
| --------------------------- | --------------------------- |
| Ordered                     | Unordered (in old versions) |
| Indexed by numbers          | Indexed by keys             |
| Use when items are sequence | Use when data is key-value  |

### **Dictionary Methods**

### **1. keys()**

Returns all keys

### **2. values()**

Returns all values

### **3. items()**

Returns key-value pairs

### **4. get()**

Safe access without error

### **5. update()**

Adds multiple values

Example:

```python
d = {"name":"Dev", "age":21}
d.update({"city":"Kanpur"})
```

---

# ✅ **SECTION 4 — Attempt ANY ONE (10 marks)**

---

# **Q4(a) ITERATORS + FILE WRITE PROGRAM**

### **Iterator Definition**

An iterator is an object that allows you to loop over elements.

To create iterator:

* Use `iter()`
* Get next value using `next()`

Example:

```python
numbers = [10, 20, 30]
it = iter(numbers)  # create iterator

print(next(it))  # 10
print(next(it))  # 20
print(next(it))  # 30
```

---

# **Creating a Text File**

```python
f = open("output.txt", "w")
f.write("Hello")
f.close()
```

---

# **Program: Count letters and digits and write to file**

```python
def write_counts(text):
    letters = digits = 0

    for ch in text:
        if ch.isalpha():
            letters += 1
        elif ch.isdigit():
            digits += 1

    with open("result.txt", "w") as f:
        f.write(f"Letters: {letters}\n")
        f.write(f"Digits: {digits}\n")

# Example
write_counts("Hello1234")
```

---

# **Q4(b) TYPES OF INHERITANCE**

1. **Single Inheritance**

```python
class A:
    pass
class B(A):
    pass
```

2. **Multiple**

```python
class B(A, C):
    pass
```

3. **Multilevel**

```python
class A: pass
class B(A): pass
class C(B): pass
```

4. **Hierarchical**
   One parent, many children.

---

# **Static, Instance, Class Methods**

```python
class Demo:
    def __init__(self):
        self.x = 10  # instance variable

    def instance_method(self):
        print(self.x)

    @classmethod
    def class_method(cls):
        print("Class method")

    @staticmethod
    def static_method():
        print("Static method")
```