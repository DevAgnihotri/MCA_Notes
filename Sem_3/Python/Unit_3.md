# Python Unit 3: Dictionaries and Functions

---

## 📚 Dictionaries

---

### What is a Dictionary?

A **dictionary** in Python is a powerful data structure that lets you store and organize data using key-value pairs. Think of it like a real dictionary, where you look up a word (key) to find its meaning (value). Dictionaries are used everywhere in Python—from storing user profiles to counting word frequencies in a text.

- **Feature Highlights:**
  - Fast lookups: Find values quickly using keys.
  - Flexible: Store any type of value, including lists and other dictionaries.
  - Dynamic: Add, update, or remove items anytime.
  - Unique keys: Each key must be unique and immutable (cannot change).
  - Mutable: You can change the contents after creation.

---

### Syntax

```python
dict_name = {key1: value1, key2: value2, ...}
```

### Example

```python
student = {"name": "Alice", "age": 20, "grade": "A"}
print(student)
```

**Output:**

```
{'name': 'Alice', 'age': 20, 'grade': 'A'}
```

---

### Accessing Values

You can get a value by using its key:

```python
print(student["name"])  # Output: Alice
```

---

### Working with Dictionaries

You can add, update, or delete items easily:

```python
student["age"] = 21  # Update value
student["city"] = "Delhi"  # Add new key-value pair
print(student)
del student["grade"]  # Delete a key-value pair
print(student)
```

**Output:**

```
{'name': 'Alice', 'age': 21, 'grade': 'A', 'city': 'Delhi'}
{'name': 'Alice', 'age': 21, 'city': 'Delhi'}
```

---

### Properties of Dictionaries

- **Unordered:** Items do not have a fixed position (before Python 3.7).
- **Mutable:** You can change, add, or remove items.
- **Keys:** Must be unique and immutable (like strings, numbers, tuples).
- **Values:** Can be any data type.
- **Real-life use:** Storing student records, configuration settings, or JSON data.

---

### Dictionary Methods & Functions

| Method/Function      | Description                      | Example                          | Output                                                            |
| -------------------- | -------------------------------- | -------------------------------- | ----------------------------------------------------------------- |
| `len(dict)`          | Number of items                  | `len(student)`                   | `3`                                                               |
| `dict.keys()`        | All keys                         | `student.keys()`                 | `dict_keys(['name', 'age', 'city'])`                              |
| `dict.values()`      | All values                       | `student.values()`               | `dict_values(['Alice', 21, 'Delhi'])`                             |
| `dict.items()`       | All key-value pairs              | `student.items()`                | `dict_items([('name', 'Alice'), ('age', 21), ('city', 'Delhi')])` |
| `dict.get(key)`      | Value for key, None if missing   | `student.get('grade')`           | `None`                                                            |
| `dict.pop(key)`      | Removes key, returns value       | `student.pop('age')`             | `21`                                                              |
| `dict.update({...})` | Updates with new key-value pairs | `student.update({'grade': 'A'})` | Adds/updates 'grade'                                              |
| `dict.clear()`       | Removes all items                | `student.clear()`                | `{}`                                                              |

---

### Looping Through a Dictionary

```python
for key, value in student.items():
    print(key, value)
```

**Output:**

```
name Alice
age 21
city Delhi
```

---

## 🚀 Functions

---

### What is a Function?

A **function** is a reusable block of code that performs a specific task. Functions help you organize your code, avoid repetition, and make your programs easier to read and maintain. Python has many built-in functions, and you can create your own too!

- **Feature Highlights:**
  - Reusable: Write once, use many times.
  - Organized: Break big problems into smaller pieces.
  - Flexible: Accept different types and numbers of arguments.
  - Return values: Functions can give back results to use elsewhere.
  - Scope: Variables inside a function are separate from those outside.

---

### Syntax

```python
def function_name(parameters):
    # code block
    return value
```

---

### Example: Defining & Calling a Function

```python
def greet(name):
    print("Hello,", name)

greet("Bob")
```

**Output:**

```
Hello, Bob
```

---

### Arguments: Mutable & Immutable

- **Immutable:** int, float, string, tuple. Their value cannot be changed inside the function.
- **Mutable:** list, dict. Their value can be changed inside the function.

**Example:**

```python
def change_number(x):
    x = x + 5
    print("Inside function:", x)
num = 10
change_number(num)
print("Outside function:", num)
```

**Output:**

```
Inside function: 15
Outside function: 10
```

```python
def add_item(mylist):
    mylist.append(4)
    print("Inside function:", mylist)
nums = [1, 2, 3]
add_item(nums)
print("Outside function:", nums)
```

**Output:**

```
Inside function: [1, 2, 3, 4]
Outside function: [1, 2, 3, 4]
```

---

### Types of Arguments

| Type            | Description                                           | Example                          |
| --------------- | ----------------------------------------------------- | -------------------------------- |
| Positional      | Arguments matched by position                         | `def add(a, b):` `add(2, 3)`     |
| Keyword         | Arguments matched by name                             | `def add(a, b):` `add(a=2, b=3)` |
| Default         | Arguments with default values                         | `def greet(name, msg="Hi"): ...` |
| Variable-length | Accepts any number of arguments (`*args`, `**kwargs`) | `def show(*args): ...`           |

---

### Example: Variable-length Arguments

```python
def show(*args):
    print(args)
show(1, 2, 3)
```

**Output:**

```
(1, 2, 3)
```

---

### Recursion

Recursion is when a function calls itself to solve a problem. This is useful for tasks like calculating factorials or searching in trees.

**Example:**

```python
def factorial(n):
    if n == 1:
        return 1
    else:
        return n * factorial(n-1)
print(factorial(5))
```

**Output:**

```
120
```

---

### Scope of Variables

- **Local Scope:** Variable defined inside a function, only accessible there.
- **Global Scope:** Variable defined outside all functions, accessible everywhere.

**Example:**

```python
global_var = 10
def show():
    local_var = 5
    print("Local:", local_var)
    print("Global:", global_var)
show()
```

**Output:**

```
Local: 5
Global: 10
```

---

### Advanced Features & Best Practices

- **Return Multiple Values:** Functions can return more than one value using tuples.
- **Nested Functions:** You can define a function inside another function for better organization.
- **Default Arguments:** Make your functions flexible by providing default values.
- **Docstrings:** Add a description to your function using triple quotes so others know what it does.
- **Type Hints:** Help others understand what type of arguments your function expects.

**Example: Returning multiple values**

```python
def get_stats(numbers):
    total = sum(numbers)
    count = len(numbers)
    return total, count
nums = [1, 2, 3]
total, count = get_stats(nums)
print("Total:", total)
print("Count:", count)
```

**Output:**

```
Total: 6
Count: 3
```

**Example: Default argument**

```python
def greet(name, msg="Hello"):
    print(msg, name)
greet("Sam")
greet("Sam", "Hi")
```

**Output:**

```
Hello Sam
Hi Sam
```

---

## ⭐ Summary: Why Use Dictionaries & Functions?

- Dictionaries and functions are the backbone of Python programming.
- They help you write clean, organized, and powerful code.
- Mastering these topics will make you a better Python developer and help you build amazing projects!

---

# End of Notes
