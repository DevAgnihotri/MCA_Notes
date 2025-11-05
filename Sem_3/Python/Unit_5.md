# Python Unit 5 — Exception Handling (Simple English)

## Table of Contents

- [What is an Exception?](#what-is-an-exception)
- [Why handle exceptions?](#why-handle-exceptions)
- [Basic try / except syntax](#basic-try--except-syntax)
- [Except clause variations](#except-clause-variations)
- [else clause](#else-clause)
- [finally clause](#finally-clause)
- [Raising exceptions (`raise`)](#raising-exceptions-raise)
- [User-defined exceptions](#user-defined-exceptions)
- [Common built-in exceptions (short list)](#common-built-in-exceptions-short-list)
- [Good practices and tips](#good-practices-and-tips)
- [Basics of Python for Data Analysis](#basics-of-python-for-data-analysis)
- [Introduction to Series and DataFrames](#introduction-to-series-and-dataframes)

---

## What is an Exception?

- Definition: An exception is an error that happens while a program runs. It stops the normal flow of the program.
- Example: dividing by zero, opening a file that doesn't exist, or converting text to a number when the text is not a number.

## Why handle exceptions?

- If you do not handle exceptions, the program will stop and show an error message.
- Handling exceptions lets your program continue or exit cleanly and lets you show helpful messages to the user.

## Basic try / except syntax

- Use `try` to wrap code that might cause an exception.
- Use `except` to catch and handle the exception.

Example:

```python
try:
    x = int(input('Enter a number: '))
    print('You entered', x)
except ValueError:
    print('That was not a valid number.')
```

Explanation: If the user types something that cannot be converted to an integer, Python raises a `ValueError`. The `except` block runs and prints a friendly message instead of crashing.

## Except clause variations

- Catch a specific exception:

```python
try:
    ...
except FileNotFoundError:
    print('File not found')
```

- Catch multiple specific exceptions (tuple):

```python
try:
    ...
except (ValueError, TypeError):
    print('Value or type error')
```

- Catch any exception (not recommended unless needed):

```python
try:
    ...
except Exception as e:
    print('Something went wrong:', e)
```

Note: `except Exception` catches most errors but not system-exiting exceptions like `SystemExit` and `KeyboardInterrupt` unless you include them. Use it carefully.

## else clause

- `else` runs only when no exception happened in the `try` block.

```python
try:
    result = 10 / 2
except ZeroDivisionError:
    print('Cannot divide by zero')
else:
    print('Division successful, result =', result)
```

## finally clause

- `finally` runs always, whether an exception happened or not.
- Use it to clean up resources (close files, release locks).

```python
try:
    f = open('data.txt')
    data = f.read()
except FileNotFoundError:
    print('File not found')
finally:
    try:
        f.close()
    except NameError:
        pass
```

Better pattern uses `with` for files (so `finally` is not needed):

```python
with open('data.txt') as f:
    data = f.read()
# file closed automatically
```

## Raising exceptions (`raise`)

- Use `raise` when your code finds a problem and you want to stop or inform the caller.

Example:

```python
def divide(a, b):
    if b == 0:
        raise ValueError('b must not be zero')
    return a / b

try:
    print(divide(10, 0))
except ValueError as e:
    print('Error:', e)
```

## User-defined exceptions

- You can make your own exception classes by inheriting from `Exception`.

Simple example:

```python
class MyError(Exception):
    """Custom exception for my program"""
    pass

def do_work(x):
    if x < 0:
        raise MyError('x must be non-negative')
    return x * 2

try:
    do_work(-1)
except MyError as e:
    print('Caught my error:', e)
```

- You can add `__init__` to pass extra info and properties to your exception class.

## Common built-in exceptions (short list)

- `ValueError` — wrong value for a function (e.g., int('a')).
- `TypeError` — wrong type (e.g., adding string and number).
- `ZeroDivisionError` — division by zero.
- `FileNotFoundError` / `OSError` — file or OS errors.
- `KeyError` — missing key in a dictionary.

## Good practices and tips

- Catch specific exceptions, not everything. This prevents hiding bugs.
- Use `with` for files and resources when possible.
- Clean up in `finally` if you cannot use a context manager.
- Add helpful messages when raising exceptions.
- Re-raise exceptions when you cannot handle them (use `raise` alone inside `except` to re-raise).
- Do not use exceptions for normal control flow; use them for errors.

---

If you want, I can now:

- add 3 practice exercises with solutions, or
- create small example scripts under `examples/` and link them here, or
- simplify further for younger students.

---

## Basics of Python for Data Analysis

These notes explain the basic ideas you need to start using Python for data analysis. I will keep the language simple.

### What is data analysis?

- Data analysis means looking at data to understand it and find useful information.
- People use Python because it has good tools that make working with tables and numbers easy.

### Main Python tools (short list)

- `numpy` — for fast number arrays and math.
- `pandas` — for tables (Series and DataFrame) and easy data handling.
- `matplotlib` / `seaborn` — for making charts (plots) to see the data.

### Installing the main packages (PowerShell)

```powershell
python -m pip install --upgrade pip
python -m pip install numpy pandas matplotlib seaborn
```

### Typical data-analysis workflow

1. Load data (CSV, Excel, database).
2. Look at the data (head, shape, types).
3. Clean the data (fix missing values, wrong types).
4. Analyze (group, summarize, statistics).
5. Visualize (plots) and save results.

### Quick example (read CSV and inspect)

```python
import pandas as pd

df = pd.read_csv('data.csv')   # load a CSV file into a DataFrame
print(df.shape)                # number of rows and columns
print(df.head())               # first five rows
print(df.describe())           # basic statistics for numeric columns
```

Key points:

- Use `df.head()` to quickly see the top rows.
- Use `df.info()` to check data types and missing values.
- Use `df.describe()` for numeric summaries (mean, std, min, max).

---

## Introduction to Series and DataFrames

These are the most important data structures in `pandas`.

### What is a Series?

- A `Series` is like a column in a table. It has values and an index (row labels).
- Think of it as a one-column table.

Example:

```python
import pandas as pd

s = pd.Series([10, 20, 30], index=['a', 'b', 'c'])
print(s)
print(s['b'])   # access by index label
```

### What is a DataFrame?

- A `DataFrame` is a table with rows and columns, like a spreadsheet or SQL table.
- Columns are `Series` objects with the same index (row labels).

Create a DataFrame example:

```python
data = {
    'name': ['Alice', 'Bob', 'Charlie'],
    'age': [25, 30, 22],
    'score': [85.5, 92.0, 78.0]
}
df = pd.DataFrame(data)
print(df)
```

### Common DataFrame operations (simple)

- Select a column: `df['age']` (returns a Series)
- Select multiple columns: `df[['name', 'score']]`
- Select rows by position: `df.iloc[0]` or `df.iloc[0:3]`
- Select rows by label (if index is labeled): `df.loc['row_label']`
- Filter rows: `df[df['age'] > 25]`
- Add a new column: `df['passed'] = df['score'] > 80`
- Drop columns: `df.drop(columns=['score'])`

Example — filter and add column:

```python
adults = df[df['age'] >= 25]
df['passed'] = df['score'] >= 80
print(adults)
print(df)
```

### Handling missing data (simple rules)

- Check for missing values: `df.isna().sum()` shows how many missing per column.
- Remove rows with missing values: `df.dropna()`
- Fill missing values: `df.fillna(0)` or `df['col'].fillna(df['col'].mean())`

### Grouping and summarizing (example)

```python
# group by a column and get mean of each group
grouped = df.groupby('name')['score'].mean()
print(grouped)
```

### Saving results

- Save cleaned table to CSV: `df.to_csv('clean.csv', index=False)`
- Save to Excel: `df.to_excel('clean.xlsx', index=False)` (requires openpyxl or similar)

### Simple tips for beginners

- Work step-by-step: load, inspect, clean, analyze, visualize.
- Use small code and print intermediate results.
- Keep backups of original data files.

---

If you want, I can now:

- add 3 practice exercises with answers for Series/DataFrame, or
- create an `examples/` folder with small runnable scripts (CSV reading, cleaning, simple plot) and link them here.
