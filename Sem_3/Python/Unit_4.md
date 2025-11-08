# Python Unit 4 — Modules, Packages & Selected Standard Library Modules

## Table of Contents

- [Modules and Packages — Overview](#modules-and-packages---overview)
- [User-defined Modules](#user-defined-modules)
  - [Create a module](#create-a-module)
  - [Import styles and examples](#import-styles-and-examples)
  - [The **name** guard](#the-name-guard)
  - [Packages and `__init__.py`](#packages-and-__init__py)
- [Standard Library Modules — Quick Guide](#standard-library-modules---quick-guide)
  - [random](#random)
  - [math](#math-module)
  - [string](#string-module)
  - [sys](#sys)
  - [numpy (brief)](#numpy-brief)
  - [scipy (brief)](#scipy-brief)
  - [list (built-in)](#list-built-in)
  - [Date & Time (`datetime`)](#date--time-datetime)
  - [Regular Expressions (`re`)](#regular-expressions-re)
  - [File Handling](#file-handling)

---

## Modules and Packages - Overview

- Definition: A module is a single Python file (.py) that contains definitions (functions, classes, variables), and can be imported using the `import` keyword to be reused. A package is a collection of modules organized in folders and may include an `__init__.py` file.
- Why use them: Reuse code, organize large projects, avoid name collisions, and make testing easier.

Key ideas:

- namespace: modules create their own namespace (module.variable)
- import once per interpreter session (cached in `sys.modules`)

---

# User-defined Modules

Simple definition: A user-defined module is any `.py` file we create to hold functions, classes, or constants we want to reuse.

### Create a module

1. Make a file `mymath.py`:

```python
# mymath.py
PI = 3.14159

def add(a, b):
		return a + b

def area_circle(r):
		return PI * r * r

if __name__ == "__main__":
		# quick test when run directly
		print("area for r=2:", area_circle(2))
```

2. Use it from another file `main.py`:

```python
import mymath
print(mymath.add(3, 4))
print(mymath.area_circle(2))
```

### Import styles and examples

- `import module` — use `module.name`
- `import module as m` — shorter alias
- `from module import name` — bring `name` directly into current namespace
- `from module import *` — not recommended for large modules (pollutes namespace)

Examples:

```python
from mymath import add, area_circle
print(add(1,2))

import mymath as mm
print(mm.PI)
```

Key points:

- Prefer explicit imports (`from module import name`) for clarity.
- Use aliases when names are long or conflict with other names.

### The **name** guard

- Use `if __name__ == "__main__":` in modules to allow the file to be both importable and runnable as a script.
- When a module is imported, `__name__` is the module name; when run directly, `__name__ == "__main__"`.

### Packages and `__init__.py`

- A package is a folder containing Python modules and optionally an `__init__.py` file. In modern Python, `__init__.py` may be empty but is still commonly used.

Structure example:

```
myproject/
	mathlib/
		__init__.py
		algebra.py
		geometry.py
```

You can import with:

```python
from mathlib import algebra
from mathlib.geometry import area_circle
```

Tips:

- Keep package APIs small and clear (export only what's needed in `__init__.py`).
- Use subpackages for large projects.

---

# Standard Library Modules - Quick Guide

This section covers the requested standard and popular third-party modules: `random`, `math`, `string`, `sys`, and short notes on `numpy` and `scipy`.

### random

- Purpose: Generate random numbers and make random choices.
- Common functions:
  - `random.random()` — float in [0.0, 1.0)
  - `random.randint(a, b)` — integer between a and b inclusive
  - `random.choice(seq)` — random element from a sequence
  - `random.shuffle(list)` — shuffle list in place
  - `random.seed(x)` — set seed for reproducible results

Example:

```python
import random
random.seed(0)
print(random.random())         # deterministic when seeded
print(random.randint(1, 10))
print(random.choice(['a','b','c']))
lst = [1,2,3,4]
random.shuffle(lst)
print(lst)
```

Key points:

- Use `seed()` when you need repeatable results (tests, demos).
- For cryptographic randomness, use `secrets` module instead.

### math module

- Purpose: Mathematical functions on floats and constants.
- Common functions/constants: `math.sqrt`, `math.sin`, `math.cos`, `math.log`, `math.exp`, `math.floor`, `math.ceil`, `math.pi`, `math.e`.

Example:

```python
import math
print(math.sqrt(16))
print(math.pi)
print(math.floor(3.7), math.ceil(3.2))
```

Key points:

- `math` works on Python numbers (floats, ints). For element-wise array math use `numpy`.

## string module

- Purpose: Text helpers and constants.
- Useful items: `string.ascii_letters`, `string.ascii_lowercase`, `string.digits`, `string.punctuation`, and `string.Template`.

### Useful items in the string module — quick table

| Item                                  | What it is                                       | Example / usage                                             |
| ------------------------------------- | ------------------------------------------------ | ----------------------------------------------------------- |
| string.ascii_letters                  | All ASCII letters (lower+upper)                  | `string.ascii_letters` → "abcdefghijklmnopqrstuvwxyzA-to-Z" |
| string.ascii_lowercase                | Lowercase ASCII letters                          | `string.ascii_lowercase` → "abcdefghijklmnopqrstuvwxyz"     |
| string.ascii_uppercase                | Uppercase ASCII letters                          | `string.ascii_uppercase` → "ABCDEFGHIJKLMNOPQRSTUVWXYZ"     |
| string.digits                         | Decimal digits                                   | `string.digits` → "0123456789"                              |
| string.hexdigits                      | Hexadecimal digits                               | `string.hexdigits` → "0123456789abcdefABCDEF"               |
| string.octdigits                      | Octal digits                                     | `string.octdigits` → "01234567"                             |
| string.punctuation                    | Punctuation characters                           | `string.punctuation` → "!\"#$%&'()\*+,-./:;<=>?@[\\]^\_`{}  |
| string.printable                      | All printable chars                              | `string.printable`                                          |
| string.whitespace                     | Whitespace chars                                 | `string.whitespace` → `'\t\n\x0b\x0c\r '`                   |
| string.Template                       | Simple $-based templates for substitution        | `Template('Hi, $name').substitute(name='Ravi')`             |
| Template.substitute / safe_substitute | Substitute placeholders (safe avoids KeyError)   | `t.safe_substitute(name='Ravi')`                            |
| string.capwords(s[, sep])             | Split on whitespace, capitalize words, rejoin    | `string.capwords('hello world')` → "Hello World"            |
| string.Formatter                      | Advanced/custom formatting (parse/format fields) | `Formatter().format('{:.2f}', 3.14159)` → "3.14"            |

Examples (copy-paste):

```python
import string
from string import Template, Formatter

# constants
print(string.ascii_lowercase, string.digits)

# Template (safe_substitute avoids KeyError)
t = Template('Hello, $name! Age: $age')
print(t.substitute(name='Ravi', age=21))
print(t.safe_substitute(name='Ravi'))  # leaves $age if missing

# capwords
print(string.capwords('welcome to python'))

# remove punctuation using translate (str.maketrans)
s = "Hello, world!!!"
trans = str.maketrans('', '', string.punctuation)
print(s.translate(trans))  # "Hello world"

# Formatter basic use
fmt = Formatter()
print(fmt.format("{:.2f}", 3.14159))  # "3.14"
```

Use the constants for whitelist/charset building, the Template for simple user-facing substitutions, capwords for title-like capitalization, and Formatter when you need custom field parsing/format behavior.

Example:

```python
import string
print(string.ascii_letters)
print(string.digits)

from string import Template
t = Template('Hello, $name!')
print(t.substitute(name='Ravi'))
```

Key points:

- `str` objects have most methods; `string` provides constants and the `Template` helper.

## sys

- Purpose: Access interpreter-level information and command-line arguments.
- Common uses: `sys.argv` (command-line args), `sys.exit()` (exit program), `sys.path` (module search path), `sys.version`.

"""
| Name | Example |
|---|---|
| sys.argv | `print(sys.argv)  # ['prog.py', 'a', 'b']` |
| sys.exit | `sys.exit(1)` |
| sys.path | `sys.path.append('/my/modules')` |
| sys.modules | `print('json' in sys.modules)  # True` |
| sys.version | `print(sys.version)` |
| sys.version_info | `print(sys.version_info.major)  # 3` |
| sys.platform | `print(sys.platform)  # 'win32' | 'linux' | 'darwin'` |
| sys.executable | `print(sys.executable)` |
| sys.getrecursionlimit / sys.setrecursionlimit | `print(sys.getrecursionlimit()); sys.setrecursionlimit(2000)` |
| sys.getsizeof | `print(sys.getsizeof([1,2,3]))` |
| sys.getdefaultencoding | `print(sys.getdefaultencoding())` |
| sys.getfilesystemencoding | `print(sys.getfilesystemencoding())` |
| sys.stdin / sys.stdout / sys.stderr | `sys.stdout.write('hello\\n'); line = sys.stdin.readline()` |
| sys.byteorder | `print(sys.byteorder)  # 'little' or 'big'` |
| sys.maxsize | `print(sys.maxsize)` |
| sys.maxunicode | `print(sys.maxunicode)` |
| sys.builtin_module_names | `print('sys' in sys.builtin_module_names)` |
| sys.flags | `print(sys.flags.optimize)` |
| sys.getrefcount | `a = []; print(sys.getrefcount(a))` |
| sys.gettrace / sys.settrace | `print(sys.gettrace())  # None when not tracing` |
| sys.setprofile / sys.getprofile | `print(sys.getprofile())` |
| sys.api_version | `print(sys.api_version)` |
| sys.exitfunc (deprecated) | `# deprecated — use atexit.register(...) instead` |
"""

## numpy (brief)

- Not in the standard library; a very common third-party package for numerical computing and arrays.
- Core type: `numpy.ndarray` — fast, fixed-type arrays with vectorized operations.
 
 
### Common NumPy functions — syntax and use

| Function / Topic             |                                                         Syntax | Use / Example                                         |
| ---------------------------- | -------------------------------------------------------------: | ----------------------------------------------------- |
| Create array                 |                                    `np.array(obj, dtype=None)` | `a = np.array([1,2,3])`                               |
| Range-like                   |                                 `np.arange(start, stop, step)` | `np.arange(0,10,2)`                                   |
| Evenly spaced                |                                `np.linspace(start, stop, num)` | `np.linspace(0,1,5)`                                  |
| Zeros                        |                                  `np.zeros(shape, dtype=None)` | `np.zeros((2,3))`                                     |
| Ones                         |                                   `np.ones(shape, dtype=None)` | `np.ones(4)`                                          |
| Empty (uninitialized)        |                                              `np.empty(shape)` | `np.empty((2,2))`                                     |
| Identity matrix              |                                            `np.eye(N, M=None)` | `np.eye(3)`                                           |
| Full (fill)                  |                                   `np.full(shape, fill_value)` | `np.full((2,2), 7)`                                   |
| Range reshape                |                                      `np.reshape(a, newshape)` | `a.reshape((2,3))`                                    |
| Flatten                      |                                    `a.flatten()` / `a.ravel()` | `a.flatten()`                                         |
| Transpose                    |                                      `a.T` / `np.transpose(a)` | `a.T`                                                 |
| Concatenate                  |                                `np.concatenate((a,b), axis=0)` | `np.concatenate([a,b], axis=0)`                       |
| Stack                        |                                      `np.stack((a,b), axis=0)` | `np.stack([a,b], axis=1)`                             |
| vstack / hstack              |                         `np.vstack((a,b))`, `np.hstack((a,b))` | vertical/horizontal stack                             |
| Split                        |                     `np.split(a, indices_or_sections, axis=0)` | `np.split(a,3)`                                       |
| Tile / Repeat                |                    `np.tile(a, reps)`, `np.repeat(a, repeats)` | repeat blocks / elements                              |
| Shape / ndim / size          |                                  `a.shape`, `a.ndim`, `a.size` | inspect array structure                               |
| dtype / astype               |                               `a.dtype`, `a.astype(new_dtype)` | `a.astype(float)`                                     |
| itemsize / nbytes            |                                       `a.itemsize`, `a.nbytes` | memory per element / total bytes                      |
| sum / mean / prod            |                           `np.sum(a, axis=None)`, `np.mean(a)` | reductions; `np.sum(a,axis=1)`                        |
| std / var                    |                                       `np.std(a)`, `np.var(a)` | standard deviation / variance                         |
| min / max / argmin / argmax  |                             `np.min(a)`, `np.argmax(a,axis=0)` | find extremes and indices                             |
| unique                       |                            `np.unique(a, return_counts=False)` | `np.unique(arr, return_counts=True)`                  |
| where                        |                                    `np.where(condition, x, y)` | conditional selection or indices                      |
| nonzero                      |                                                `np.nonzero(a)` | indices of non-zero elements                          |
| clip                         |                                     `np.clip(a, a_min, a_max)` | clamp values                                          |
| sort / argsort               |                                  `np.sort(a)`, `np.argsort(a)` | sorted array / index order                            |
| searchsorted                 |                                 `np.searchsorted(sorted_a, v)` | insertion index in sorted array                       |
| dot / matmul                 |                                         `np.dot(a,b)`, `a @ b` | matrix / vector multiplication                        |
| tensordot                    |                                  `np.tensordot(a,b, axes=...)` | generalized contraction                               |
| cross                        |                                                `np.cross(a,b)` | 3D vector cross product                               |
| outer                        |                                                `np.outer(a,b)` | outer product                                         |
| broadcast_to                 |                                    `np.broadcast_to(a, shape)` | view with broadcasted shape                           |
| logical ops                  |                     `np.logical_and(a,b)`, `np.logical_not(a)` | elementwise boolean ops                               |
| any / all                    |                                 `np.any(cond)`, `np.all(cond)` | existential / universal checks                        |
| clip / round                 |                  `np.clip(a, mn, mx)`, `np.round(a, decimals)` | clamp and round values                                |
| sqrt / sin / cos / exp / log |                         `np.sqrt(a)`, `np.exp(a)`, `np.log(a)` | elementwise math                                      |
| polynomial helpers           |                       `np.polyfit(x,y,deg)`, `np.polyval(p,x)` | fit/evaluate polynomials                              |
| random (generator)           |                                      `np.random.default_rng()` | prefer Generator API: `rng = np.random.default_rng()` |
| random methods (Generator)   |                   `rng.integers(low,high)`, `rng.random(size)` | `rng.integers(0,10, size=5)`                          |
| legacy random                |                        `np.random.rand()`, `np.random.randn()` | `np.random.rand(3)` (use Generator when possible)     |
| save / load                  |                          `np.save(file, arr)`, `np.load(file)` | binary .npy format                                    |
| savez / load (multiple)      |                    `np.savez(file, a=a, b=b)`, `np.load(file)` | save multiple arrays                                  |
| savetxt / loadtxt            |                    `np.savetxt(fname, a)`, `np.loadtxt(fname)` | text CSV-like I/O                                     |
| linear algebra (linalg)      |                         `np.linalg.inv(a)`, `np.linalg.det(a)` | matrix inverse, determinant                           |
| solve / eig / svd / norm     | `np.linalg.solve(A,b)`, `np.linalg.eig(A)`, `np.linalg.svd(A)` | linear solve, eigen, SVD                              |
| norm                         |                       `np.linalg.norm(x, ord=None, axis=None)` | vector/matrix norm                                    |
| conditioning / pinv          |                                            `np.linalg.pinv(a)` | pseudo-inverse                                        |
| broadcasting rules           |                                   implicit via shape alignment | e.g., `a + b` broadcasts if shapes compatible         |

Small example:

```python
import numpy as np
a = np.array([1,2,3])
b = np.arange(6).reshape(2,3)
print(a * 2)        # vectorized
print(b.sum(axis=1))
```

Key points:

- Use numpy for numeric arrays and fast element-wise operations. Python lists are not a substitute for large numeric datasets.

### scipy (brief)

- Built on top of NumPy; provides scientific algorithms (optimization, integration, statistics, signal processing).
- Install via `pip install scipy`.

Small example (statistics):

```python
from scipy import stats
print(stats.ttest_1samp([1.0,2.0,3.0], popmean=2.0))
```

Key points:

- SciPy offers specialized scientific routines. For many tasks you will use `scipy.stats`, `scipy.optimize`, or `scipy.integrate`.

---

### list (built-in)

- Purpose: `list` is a built-in mutable sequence type used to store ordered collections of items. Lists are one of Python's core data structures.
- Common operations:
  - Create: `[]`, `list()` or `list(iterable)`
  - Indexing/slicing: `a[0]`, `a[-1]`, `a[1:4]`
  - Add: `append`, `extend`, `insert`
  - Remove: `pop`, `remove`, `clear`
  - Search/inspect: `in`, `index`, `count`, `len`
  - Sort/copy: `sort`, `sorted`, `copy`

Example:

```python
# create and modify lists
a = [1, 2, 3]
a.append(4)
print(a)          # [1, 2, 3, 4]
print(a[0], a[-1])

b = ['a', 'b', 'c']
b.extend(['d','e'])
print(b)

# slicing
print(a[1:3])     # [2, 3]

# remove and pop
v = a.pop()       # removes last element
print(v, a)

# list comprehension (very common)
squares = [x*x for x in range(6)]
print(squares)
```

Key points:

- Use list comprehensions for readable, fast list creation.
- For large numerical arrays prefer `numpy` arrays (memory & speed benefits).
- Remember `list.sort()` sorts in-place and returns None; `sorted(list)` returns a new list.

### Date & Time (`datetime`)

- Purpose: The `datetime` module provides classes for manipulating dates and times: `date`, `time`, `datetime`, `timedelta`, and `timezone`.
- Common uses:
  - `datetime.datetime.now()` — current local date & time
  - `datetime.date.today()` — current date
  - `datetime.timedelta(days=1)` — difference between dates/times
  - Parsing/formatting: `strftime` and `strptime`

Example:

```python
from datetime import datetime, date, timedelta

now = datetime.now()
print('Now:', now)

today = date.today()
print('Today:', today)

tomorrow = today + timedelta(days=1)
print('Tomorrow:', tomorrow)

# formatting
print(now.strftime('%Y-%m-%d %H:%M:%S'))

# parsing from string
dt = datetime.strptime('2025-11-05 14:30', '%Y-%m-%d %H:%M')
print(dt)
```

Key points:

- Use `timezone` aware datetimes when working across zones. Prefer `datetime.now(timezone.utc)` or use `pytz` / `zoneinfo` (Python 3.9+) for robust timezone handling.
- `timedelta` is useful for adding/subtracting time intervals.

### Regular Expressions (`re`)

- Purpose: The `re` module provides tools for pattern matching and text processing using regular expressions.
- Core functions:
  - `re.match(pattern, string)` — attempts to match pattern at the start of the string
  - `re.search(pattern, string)` — searches for the first occurrence anywhere in the string
  - `re.findall(pattern, string)` — returns all non-overlapping matches as a list
  - `re.finditer(pattern, string)` — returns an iterator of match objects
  - `re.sub(pattern, repl, string)` — replace matches with `repl`
  - `re.compile(pattern, flags=0)` — compile a pattern for reuse

Examples:

```python
import re

text = 'Contact: alice@example.com, bob@work.net'

# search for an email anywhere
m = re.search(r'[\w.-]+@[\w.-]+', text)
if m:
    print('first email:', m.group(0))

# findall returns all matches
emails = re.findall(r'[\w.-]+@[\w.-]+', text)
print('all emails:', emails)

# replace email domain
new = re.sub(r'@example\.com', '@example.org', text)
print(new)

# match only checks from start
print(bool(re.match(r'Contact:', text)))  # True

# compile a pattern for repeated use
pat = re.compile(r'(\w+)@(\w+\.\w+)')
for mo in pat.finditer(text):
    print('user:', mo.group(1), 'domain:', mo.group(2))
```

Key points:

- Use raw strings (r'...') for regex patterns to avoid backslash escapes.
- `re.match` vs `re.search`: `match` anchors to the start; `search` looks everywhere.
- Prefer `re.compile` when running the same pattern many times (small speed gain and clearer code).
- Regular expressions are powerful but can become hard to read; prefer simple string methods when possible.

---

## How to install & run examples

- To install numpy and scipy (Windows / PowerShell):

```powershell
python -m pip install --upgrade pip
python -m pip install numpy scipy
```

- To run a Python example file (PowerShell):

```powershell
python main.py
```

Notes about environments:

- Prefer using a virtual environment (`python -m venv .venv`) and activating it before installing packages.

---

## File Handling

These notes explain how to work with files in Python. I am writing in simple, easy English so it is clear for everyone.

### 1) Introduction

- A file is a place on your computer where data is stored. Files can be text files (like notes) or binary files (like images).
- File handling means opening a file, reading or writing data, and then closing the file.

### 2) File types

- Text files: store readable characters. Example: `.txt`, `.csv`, `.py`.
- Binary files: store bytes. Example: `.jpg`, `.png`, `.exe`, many data files.

Be careful: open text with text modes and binary with binary modes.

### 3) Creating, Opening and Closing files

- Use `open()` to open or create a file. Always close files when done.
- The simplest way is using a `with` statement. This makes sure the file closes automatically.

Example (create and write):

```python
# write text to a file (create or overwrite)
with open('notes.txt', 'w', encoding='utf-8') as f:
  f.write('Hello, this is my file.\n')
  f.write('Second line.')

# file is closed automatically here
```

Example (read file):

```python
with open('notes.txt', 'r', encoding='utf-8') as f:
  content = f.read()        # read the whole file as a string
  print(content)

# or read line by line
with open('notes.txt', 'r', encoding='utf-8') as f:
  for line in f:
    print(line.strip())
```

### 4) Renaming, Accessing and Deleting files

Use the `os` module for file operations like rename and delete.

```python
import os

# rename a file
os.rename('oldname.txt', 'newname.txt')

# check if file exists
print(os.path.exists('newname.txt'))

# delete a file
os.remove('newname.txt')   # careful: this deletes the file
```

For copying files use `shutil.copy()` from the `shutil` module.

### 5) File pointers (seek and tell)

- A file pointer is the place where the next read or write happens. When you open a file, the pointer starts at the beginning.
- `f.tell()` shows the current position. `f.seek(offset, whence)` moves the pointer.

Example:

```python
with open('notes.txt', 'r', encoding='utf-8') as f:
  print('start position:', f.tell())
  data = f.read(5)        # read first 5 characters
  print('after read position:', f.tell())
  f.seek(0)               # go back to start
  print('back to start:', f.tell())
```

### 6) File modes (what do the letters mean?)

- `r` : open for reading (file must exist)
- `w` : open for writing (creates or truncates file)
- `a` : open for appending (write to end of file)
- `x` : create and open for exclusive creation (fail if file exists)
- `b` : binary mode (use with others e.g. `rb`, `wb`)
- `t` : text mode (default, e.g. `rt`, `wt`)
- `+` : update (read and write) e.g. `r+`, `w+`

Examples:

```python
with open('log.txt', 'a', encoding='utf-8') as f:
  f.write('New log entry\n')   # appends to file

with open('data.bin', 'wb') as f:   # write bytes to binary file
  f.write(b'\x00\x01\x02')
```

### 7) Binary files

- Binary files store data in bytes. You must open them in binary mode (`b`).
- Use `rb` to read and `wb` to write. When you read binary data you get a `bytes` object.

Example (read an image):

```python
with open('image.jpg', 'rb') as f:
  data = f.read()
  print(type(data), len(data))   # bytes and length in bytes
```

Example (write binary):

```python
with open('out.bin', 'wb') as f:
  f.write(b'ABCD')   # write bytes
```
