# Year 2025

## SECTION A — brief answers (2 × 7 = 14 marks)

*(Each short, focused — suitable for ~2 marks each but concise and complete.)*

### a. How to handle exceptions in Python — with example

**Explanation:** Use `try`, `except` blocks to catch runtime errors (exceptions). Optionally use `else` to run code if no exception occurs, and `finally` for cleanup that must run regardless of exceptions.
**Example:**

```python
try:
    x = int(input("Enter a number: "))
    result = 10 / x
except ValueError:
    print("You must enter an integer.")
except ZeroDivisionError:
    print("Cannot divide by zero.")
else:
    print("Result is", result)
finally:
    print("Execution complete.")
```

**Key points:** prevents program crash, allows graceful handling, can catch specific exceptions or use a bare `except Exception as e:` to inspect unknown errors.

---

### b. Output of the two code snippets (explain difference)

**Code 1 (tuple input):**

```python
def compute(x):
    return [i**2 for i in x if i % 2 == 0]
print(compute((1, 2, 3, 4, 5)))
```

**Output:** `[4, 16]`
**Reason:** Tuple `(1,2,3,4,5)` is iterable; comprehension selects even numbers (2 and 4) and returns their squares `4` and `16`.

**Code 2 (list input):**

```python
def compute(x):
    return [i**2 for i in x if i % 2 == 0]
print(compute([1, 2, 3, 4, 5]))
```

**Output:** `[4, 16]`
**Reason:** Works exactly the same with a list because the comprehension only requires an iterable. No difference in output.

---

### c. Explain floor division with an example

**Definition:** Floor division `//` divides two numbers and returns the largest integer less than or equal to the exact quotient (i.e., rounds down). Works with integers and floats.
**Example:**

```python
7 // 3   # -> 2  (because 7/3 = 2.333..., floor is 2)
-7 // 3  # -> -3 (because -7/3 = -2.333..., floor is -3)
7.0 // 2 # -> 3.0 (float result)
```

**Key point:** floor division is different from integer truncation for negative numbers — it always floors (toward −∞).

---

### d. Purpose of the `with` statement in file handling

**Explanation:** `with` creates a context that automatically handles setup and teardown. For files it ensures the file is properly closed even if an error occurs. This avoids forgetting `file.close()` and resource leaks.
**Example:**

```python
with open("data.txt", "r") as f:
    text = f.read()
# f is automatically closed here
```

**Key point:** simpler, safer resource management (files, locks, network connections).

---

### e. Use of lambda functions in Python

**Definition:** A `lambda` is an anonymous (unnamed) small function defined with the `lambda` keyword, useful for short throwaway functions (often passed as arguments).
**Example:**

```python
doubler = lambda x: x * 2
print(doubler(5))  # -> 10

# used in sorting
pairs = [(1, 'b'), (2, 'a')]
pairs.sort(key=lambda p: p[1])  # sorts by second element
```

**Alternate question (assign a single value to a tuple):** To create a single-element tuple, include a trailing comma: `t = (5,)`. Without the comma `(5)` is just `5` in parentheses, not a tuple.

---

### f. Why NumPy is used instead of Python lists/arrays for math calculations

**Reasons (concise):**

1. **Performance:** NumPy arrays are stored in contiguous memory and use optimized C loops — much faster for large numerical computations.
2. **Vectorized operations:** Element-wise operations (e.g., `a + b`, `a * 2`) apply to whole arrays without Python-level loops.
3. **Memory efficiency:** Less overhead per element compared to Python objects in lists.
4. **Rich mathematical functions:** Provides linear algebra, FFT, random, statistical functions, broadcasting, etc.
   **Example:** `np.array([1,2,3]) * 2` returns `[2,4,6]` quickly without explicit loop.

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
def char_frequency(s):
    freq = {}
    for ch in s:
        freq[ch] = freq.get(ch, 0) + 1
    return freq

print(char_frequency("HELLO"))  # -> {'H':1, 'E':1, 'L':2, 'O':1}
```

**Using Counter:**

```python
from collections import Counter
print(Counter("HELLO"))
```

**Notes:** Can normalize case (`s.upper()` or `s.lower()`), ignore spaces/punctuation if required.

---

### d. Program to reverse the contents of a file by reading it character by character

**Approach:** Read whole file content and reverse; reading character by character and writing in reverse order requires storing characters (or using seek to read from end). Simpler: read content, reverse string, write to another file.

**Code (simple and reliable):**

```python
def reverse_file(input_path, output_path):
    with open(input_path, "r", encoding="utf-8") as fin:
        content = fin.read()
    reversed_content = content[::-1]  # reverses by character
    with open(output_path, "w", encoding="utf-8") as fout:
        fout.write(reversed_content)

# Usage
reverse_file("original.txt", "reversed.txt")
```

**If must read character by character (memory-conservative):** Seek from end and read backwards in chunks. That is more complex; above method suffices for typical exam question.

---

### e. Create a pie chart using matplotlib to represent data [9, 7, 5]

**Code (matplotlib):**

```python
import matplotlib.pyplot as plt

data = [9, 7, 5]
labels = ['A', 'B', 'C']  # optional labels
plt.pie(data, labels=labels, autopct='%1.1f%%', startangle=90)
plt.title("Simple Pie Chart")
plt.axis('equal')  # Equal aspect ratio ensures that pie is drawn as a circle.
plt.show()
```

**Explanation:** `autopct` displays percentage, `startangle` rotates start. `axis('equal')` makes the pie circular.

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

pattern = re.compile(r'^[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Za-z]{2,}$')

def is_valid_email(email):
    if ' ' in email:
        return False
    return bool(pattern.match(email))

# Tests:
print(is_valid_email("user@example.com"))      # True
print(is_valid_email("user name@x.com"))       # False (space)
print(is_valid_email("user@localhost"))        # False (no TLD)
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

**Alternative (return all longest if tie):**

```python
def longest_words(words):
    if not words:
        return []
    max_len = max(len(w) for w in words)
    return [w for w in words if len(w) == max_len]
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
import csv

def filter_csv_by_threshold(csv_path, column_name, threshold):
    with open(csv_path, newline='', encoding='utf-8') as csvfile:
        reader = csv.DictReader(csvfile)
        for row in reader:
            try:
                value = float(row[column_name])
            except (ValueError, KeyError):
                continue
            if value > threshold:
                print(row)

# Example usage:
# filter_csv_by_threshold("students.csv", "score", 75)
```

**Notes:** If you prefer pandas (convenient for larger tasks):

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

```python
import csv

def average_marks_per_student(csv_path):
    with open(csv_path, newline='', encoding='utf-8') as f:
        reader = csv.reader(f)
        header = next(reader)
        # assume first column is 'name', others are numeric marks
        for row in reader:
            name = row[0]
            marks = []
            for val in row[1:]:
                try:
                    marks.append(float(val))
                except ValueError:
                    pass
            avg = sum(marks)/len(marks) if marks else 0
            print(f"{name}: Average = {avg:.2f}")

# Example usage:
# average_marks_per_student("students.csv")
```

**If CSV is long or has varying columns, consider `pandas`:**

```python
import pandas as pd
df = pd.read_csv("students.csv")
# assume first column 'name', rest are marks
df['Average'] = df.iloc[:, 1:].mean(axis=1)
print(df[['name', 'Average']])
```