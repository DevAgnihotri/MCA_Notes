## String Manipulation

### Accessing Strings

In Python, a string is a sequence of characters. You can access individual characters using their index (position) starting from 0.

**Example:**

```python
s = "Hello World"  # A string
first_char = s[0]    # Access the first character, which is 'H'
print(first_char)    # Output: H
```

### Basic Operations

You can perform basic operations like concatenation (joining strings) and repetition.

**Examples:**

```python
s1 = "Hello"
s2 = "World"
# Concatenation
greeting = s1 + " " + s2
print(greeting)  # Output: Hello World

# Repetition
echo = s1 * 3
print(echo)    # Output: HelloHelloHello
```

### String Slices

String slices let you extract a part of the string by specifying a start index, an end index (non-inclusive), and an optional step.

**Example:**

```python
s = "Hello World"
# Slice from index 0 to 5 (non-inclusive of index 5)
part = s[0:5]
print(part)    # Output: Hello

# Using step to get every second character
step_slice = s[0:11:2]
print(step_slice)  # Output: HloWrd
```

### Functions and Methods with Strings

Below is a table listing common string functions and methods in Python, along with their syntax and examples:

| Name             | Syntax / Usage           | Description                                | Example & Output                                            |
| ---------------- | ------------------------ | ------------------------------------------ | ----------------------------------------------------------- |
| Length           | `len(string)`            | Returns number of characters in string     | `len("hello")` → `5`                                        |
| Uppercase        | `str.upper()`            | Converts all characters to uppercase       | `"hello".upper()` → `HELLO`                                 |
| Lowercase        | `str.lower()`            | Converts all characters to lowercase       | `"HELLO".lower()` → `hello`                                 |
| Title Case       | `str.title()`            | First character of each word to uppercase  | `"hello world".title()` → `Hello World`                     |
| Capitalize       | `str.capitalize()`       | First character uppercase, rest lowercase  | `"hello world".capitalize()` → `Hello world`                |
| Strip Whitespace | `str.strip()`            | Removes leading/trailing whitespace        | `"  hello  ".strip()` → `hello`                             |
| Left Strip       | `str.lstrip()`           | Removes leading whitespace                 | `"  hello".lstrip()` → `hello`                              |
| Right Strip      | `str.rstrip()`           | Removes trailing whitespace                | `"hello  ".rstrip()` → `hello`                              |
| Replace          | `str.replace(old, new)`  | Replaces substring with another            | `"hello world".replace("world", "Python")` → `hello Python` |
| Find             | `str.find(sub)`          | Returns lowest index of substring, else -1 | `"hello world".find("world")` → `6`                         |
| Count            | `str.count(sub)`         | Counts occurrences of substring            | `"banana".count("a")` → `3`                                 |
| Split            | `str.split(sep=None)`    | Splits string into list by separator       | `"a,b,c".split(",")` → `['a', 'b', 'c']`                    |
| Join             | `str.join(iterable)`     | Joins iterable elements into string        | `" ".join(["hello", "world"])` → `hello world`              |
| Startswith       | `str.startswith(prefix)` | Checks if string starts with prefix        | `"hello world".startswith("hello")` → `True`                |
| Endswith         | `str.endswith(suffix)`   | Checks if string ends with suffix          | `"hello world".endswith("world")` → `True`                  |
| Is Digit         | `str.isdigit()`          | True if all characters are digits          | `"12345".isdigit()` → `True`                                |
| Is Alpha         | `str.isalpha()`          | True if all characters are alphabetic      | `"abc".isalpha()` → `True`                                  |
| Is Alphanumeric  | `str.isalnum()`          | True if all characters are alphanumeric    | `"abc123".isalnum()` → `True`                               |

These are some of the most commonly used string functions and methods in Python.

---

## Lists

### Introduction

A list in Python is an ordered, mutable collection of items. Lists can hold items of different types.

**Example:**

```python
my_list = [10, 20, 30, "Python"]
print(my_list)  # Output: [10, 20, 30, 'Python']
```

### Accessing Lists

You can access items in a list by their index, just as with strings.

**Example:**

```python
my_list = ["apple", "banana", "cherry"]
first_item = my_list[0]
print(first_item)  # Output: apple
```

You can also use slicing to get a sublist.

**Example:**

```python
sub_list = my_list[0:2]  # Gets the first two items
print(sub_list)          # Output: ['apple', 'banana']
```

### Operations on Lists

Lists support many operations, such as adding, removing, and modifying elements.

**Examples:**

```python
numbers = [1, 2, 3]
# Append a new element
numbers.append(4)
print(numbers)       # Output: [1, 2, 3, 4]

# Remove an element
numbers.remove(2)
print(numbers)       # Output: [1, 3, 4]

# Inserting an element at a specific index
numbers.insert(1, 2)
print(numbers)       # Output: [1, 2, 3, 4]
```

### Working with Lists

You can loop through lists, sort them, and perform many operations using built-in functions and methods.

**Example - Looping through a list:**

```python
fruits = ["apple", "banana", "cherry"]
for fruit in fruits:
    print(fruit)
```
### Functions and Methods with Lists

Below is a table listing common list functions and methods in Python, along with their syntax and examples:

| Name             | Syntax / Usage                | Description                                   | Example & Output                                  |
| ---------------- | ---------------------------- | --------------------------------------------- | ------------------------------------------------- |
| Length           | `len(list)`                   | Returns number of items in list               | `len([1, 2, 3])` → `3`                            |
| Append           | `list.append(item)`           | Adds item to end of list                      | `[1, 2].append(3)` → `[1, 2, 3]`                  |
| Insert           | `list.insert(index, item)`    | Inserts item at given index                   | `[1, 3].insert(1, 2)` → `[1, 2, 3]`               |
| Remove           | `list.remove(item)`           | Removes first occurrence of item              | `[1, 2, 3].remove(2)` → `[1, 3]`                  |
| Pop              | `list.pop([index])`           | Removes and returns item at index (default last) | `[1, 2, 3].pop()` → `3`, list becomes `[1, 2]`    |
| Clear            | `list.clear()`                | Removes all items from list                   | `[1, 2, 3].clear()` → `[]`                        |
| Index            | `list.index(item)`            | Returns first index of item                   | `[1, 2, 3].index(2)` → `1`                        |
| Count            | `list.count(item)`            | Counts occurrences of item                    | `[1, 2, 2, 3].count(2)` → `2`                     |
| Sort             | `list.sort()`                 | Sorts list in ascending order                 | `[3, 1, 2].sort()` → `[1, 2, 3]`                  |
| Reverse          | `list.reverse()`              | Reverses the list in place                    | `[1, 2, 3].reverse()` → `[3, 2, 1]`               |
| Copy             | `list.copy()`                 | Returns a shallow copy of the list            | `[1, 2, 3].copy()` → `[1, 2, 3]`                  |
| Extend           | `list.extend(iterable)`       | Adds all items from iterable to end of list   | `[1, 2].extend([3, 4])` → `[1, 2, 3, 4]`          |
| Max              | `max(list)`                   | Returns largest item in list                  | `max([1, 2, 3])` → `3`                            |
| Min              | `min(list)`                   | Returns smallest item in list                 | `min([1, 2, 3])` → `1`                            |
| Sum              | `sum(list)`                   | Returns sum of items in list                  | `sum([1, 2, 3])` → `6`                            |

These are some of the most commonly used list functions and methods in Python.

---

## Tuples

### Introduction

A tuple is similar to a list but it is immutable (unchangeable). Tuples are often used to store fixed collections of items.

**Example:**

```python
tuple_example = (10, 20, 30)
print(tuple_example)  # Output: (10, 20, 30)
```

### Accessing Tuples

Like lists and strings, you can access elements in a tuple by their index and use slicing.

**Example:**

```python
t = ("a", "b", "c", "d")
print(t[1])         # Output: b
print(t[1:3])       # Output: ('b', 'c')
```

### Operations on Tuples

Since tuples are immutable, you cannot modify them after creation. However, you can perform operations like concatenation and repetition.

**Example:**

```python
t1 = (1, 2)
t2 = (3, 4)
# Concatenation
t_concat = t1 + t2
print(t_concat)   # Output: (1, 2, 3, 4)

# Repetition
t_repeat = t1 * 3
print(t_repeat)   # Output: (1, 2, 1, 2, 1, 2)
```

### Functions and Methods with Tuples

Below is a table listing common tuple functions and methods in Python, along with their syntax and examples:

| Name    | Syntax / Usage         | Description                                 | Example & Output                          |
| ------- | --------------------- | ------------------------------------------- | ----------------------------------------- |
| Length  | `len(tuple)`          | Returns number of elements in tuple         | `len((1, 2, 3))` → `3`                   |
| Count   | `tuple.count(item)`   | Counts occurrences of item                  | `(1, 2, 2, 3).count(2)` → `2`            |
| Index   | `tuple.index(item)`   | Returns first index of item                 | `(1, 2, 3).index(2)` → `1`               |
| Max     | `max(tuple)`          | Returns largest item in tuple               | `max((1, 5, 3))` → `5`                   |
| Min     | `min(tuple)`          | Returns smallest item in tuple              | `min((1, 5, 3))` → `1`                   |
| Sum     | `sum(tuple)`          | Returns sum of items in tuple (if numeric)  | `sum((1, 2, 3))` → `6`                   |

These are some of the most commonly used tuple functions and methods in Python.
