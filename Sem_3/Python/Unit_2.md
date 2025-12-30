## Strings and String Manipulation

A string is used to store text in Python.
It is written inside quotes (" " or ' ').

**How Strings Are Stored in Python**

- In Python, a string is stored as a sequence of characters.
- Each character in the string is stored one by one in memory.
- Every character has a Unicode value (like ASCII for English letters).
- Python stores the string in continuous memory locations.
- Each character is given an index number, starting from 0.

# **1. String Creation, Indexing, Slicing**

### **String Creation**

A string is made using quotes:

```python
s = "hello"
```

### **Indexing (picking one character)**

Characters have positions (index starts from 0):

```
h  e  l  l  o
0  1  2  3  4
```

Example:

```python
s[1]   # 'e'
```

### **Slicing (picking a part of string)**

```python
s[1:4]    # 'ell'
s[:3]     # 'hel'
s[::2]    # skipping → 'hlo'
```

---

### **2. Immutability of Strings**

* **Strings cannot be changed after creation.**
* You cannot do this:

```python
s = "hello"
s[0] = "y"   # ❌ error
```

You must create a **new** string:

```python
s = "y" + s[1:]
```

---

### **3. String Methods**

🔤 **Mnemonic: `SLICEFORMAT`**

Now relate each letter to common string methods:

* **S** → `strip()`, `split()`, `startswith()`
* **L** → `lower()`, `ljust()`, `len()`
* **I** → `isalnum()`, `isalpha()`, `isdigit()`
* **C** → `count()`, `capitalize()`
* **E** → `endswith()`, `encode()`
* **F** → `find()`, `format()`
* **O** → `ord()`
* **R** → `replace()`, `rfind()`
* **M** → `upper()` *(M → Make uppercase)*
* **A** → `append()` *(string concept in joins)*
* **T** → `title()` , --- `join()`


| Method      | Meaning                    | Example                                |
| ----------- | -------------------------- | -------------------------------------- |
| `upper()`   | Make all letters uppercase | `"hi".upper()` → `"HI"`                |
| `lower()`   | Make all letters lowercase | `"HI".lower()` → `"hi"`                |
| `split()`   | Break string into list     | `"a b c".split()` → `['a','b','c']`    |
| `join()`    | Join list into string      | `" ".join(['a','b'])` → `"a b"`        |
| `replace()` | Replace part of string     | `"hello".replace("l","x")` → `"hexxo"` |
| `find()`    | Find index of a word       | `"hello".find("l")` → `2`              |
| `count()`   | Count how many times       | `"hello".count("l")` → `2`             |

---

### **4. String Formatting**

#### **f-string (modern, easiest)**

```python
name = "Dev"
print(f"Hello {name}")
```

#### **format()**

```python
print("Hello {}".format(name))
```

#### **% formatting (old style)**

```python
print("Hello %s" % name)
```

---

### **5. Reversing a String**

```python
s = "hello"
rev = s[::-1]
print(rev)    # 'olleh'
```

---

### **6. Checking Palindrome**

Palindrome = same forward and backward

```python
s = "madam"
print(s == s[::-1])   # True
```

---

### **7. Removing Duplicates From String**

Keep characters only once:

```python
s = "banana"
result = ""
for ch in s:
    if ch not in result:
        result += ch
print(result)    # 'ban'
```

# List

A list in Python is an ordered, mutable collection of items. Lists can hold items of different types.

### 🔑 **`AIREPCMS`**

Break it like this:

* **A** → `append()`
* **I** → `insert()`
* **R** → `remove()`
* **E** → `extend()`
* **P** → `pop()`
* **C** → `clear()` , `count()`
* **M** → `max()`, `min()`
* **S** → `sort()`, `sum()`

## **List Creation**

Lists store multiple values inside **square brackets** `[]`.

### **Syntax**

```python
list_name = [item1, item2, item3]
```

### **Example**

```python
l = [10, 20, 30, "hello", 3.5]
```

Python lists are **dynamic** (size can grow or shrink) and **mutable** (you can change values).

---

## **Indexing**

Index = position number.
Starts from **0** for the first element.

### **Syntax**

```python
list_name[index]
```

### Example

```python
l[0]  # 10
l[3]  # "hello"
```

Negative indexing:

```python
l[-1]  # last element
```

---

## **Slicing**

Used to take a **part** of the list.

### **Syntax**

```python
list_name[start : end : step]
```

### Examples

```python
l[1:4]     # items from index 1 to 3
l[:3]      # first three elements
l[::-1]    # reverse list
```

---

## **2. Adding / Removing Elements**

Lists allow changing content.

### **1. append(x)**

Adds **one** item at the end.

```python
l.append(50)
```

### **2. extend(list)**

Adds **multiple** items.

```python
l.extend([60, 70])
```

### **3. insert(i, x)**

Add x at index i.

```python
l.insert(1, 99)
```

---

### **4. pop(i)**

Removes item at index i and returns it.

```python
l.pop(2)
```

### **5. remove(x)**

Removes first occurrence of value x.

```python
l.remove(20)
```

---

## **3. List Comprehension (VERY IMPORTANT)**

A shorter way to create new lists using a **loop inside brackets**.

### **Syntax**

```python
new_list = [expression for item in iterable if condition]
```

### **Example**

Squares of numbers:

```python
sq = [i*i for i in range(5)]
```

Only even numbers:

```python
evens = [i for i in range(10) if i % 2 == 0]
```

Used because it is **clean, fast, and most-likely asked in interviews**.

---

## **4. Sorting & Reversing Lists**

### **Sorting**

```python
l.sort()                 # ascending
l.sort(reverse=True)     # descending
```

### **Reversing**

```python
l.reverse()
```

---

## **5. Nested Lists & Matrix Operations**

A nested list is a **list inside another list**.

### **Example**

```python
mat = [
    [1,2,3],
    [4,5,6],
    [7,8,9]
]
```

### **Accessing items**

```python
mat[1][2]   # 6
```

### **Looping through a matrix**

```python
for row in mat:
    for val in row:
        print(val)
```

---

## **6. Interview Problems**

#### **a) Find Max / Min**

```python
mx = max(l)
mn = min(l)
```

#### **b) Find Duplicates** and removing them

```python
dup = [x for x in l if l.count(x) > 1]
```

```python
def remove_duplicates(s):
    result = ""
    for ch in s:
        if ch not in result:
            result += ch
    return result

print(remove_duplicates("programming"))
```

#### **c) Rotate List (right by 1)**

```python
l = l[-1:] + l[:-1]
```

#### **d) Flatten Nested List**

```python
flat = [num for row in mat for num in row]
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

## 📋 **List vs Tuple (10 Important Differences)**

| No. | Feature         | **List**                            | **Tuple**                                |
| --- | --------------- | ----------------------------------- | ---------------------------------------- |
| 1   | Mutability      | **Mutable** (values can be changed) | **Immutable** (values cannot be changed) |
| 2   | Brackets        | Uses `[ ]`                          | Uses `( )`                               |
| 3   | Add Elements    | Can add elements                    | Cannot add elements                      |
| 4   | Remove Elements | Can remove elements                 | Cannot remove elements                   |
| 5   | Modify Elements | Can modify elements                 | Cannot modify elements                   |
| 6   | Methods         | Many methods available              | Very few methods                         |
| 7   | Speed           | Slower                              | Faster                                   |
| 8   | Memory          | Uses more memory                    | Uses less memory                         |
| 9   | Safety          | Less safe (data can change)         | More safe (data fixed)                   |
| 10  | Use Case        | When data changes often             | When data should not change              |

# Tuples

A tuple is similar to a list but it is immutable (unchangeable). Tuples are often used to store fixed collections of items.

## 📦 **TUPLE Methods Mnemonic**

### 🔑 **`CI`**

* **C** → `count()`
* **I** → `index()`

## **1. Tuple Creation and Immutability**

A **tuple** is like a list but **cannot be changed** (immutable).
Tuples use **round brackets** `()`.

### ✔ Syntax

```python
t = (10, 20, 30)
```

#### ✔ Mixed data allowed

```python
t = (1, "hi", 3.5)
```

#### ✔ Immutability

You **cannot** change values:

```python
t[0] = 99   # ❌ error
```

Tuples are used when you want **fixed data** that should not be edited.

---

## ✅ **2. Tuple Packing / Unpacking**

#### ✔ Tuple Packing

Putting many values into one variable:

```python
t = 10, 20, 30   # brackets optional
```

#### ✔ Tuple Unpacking

Taking values out into separate variables:

```python
a, b, c = t
print(a, b, c)   # 10 20 30
```

You must match the number of items.

---

## ✅ **3. Tuple Methods**

Tuples have very few methods because they are **immutable**.

#### **1️⃣ count()**

Counts how many times a value appears.

```python
t = (1,2,2,3)
t.count(2)     # 2
```

#### **2️⃣ index()**

Gives the first index of a value.

```python
t.index(3)     # 3 is at index 3
```

---

### **4. When to Use Tuple vs List**

| Use Case                       | Choose    | Reason                      |
| ------------------------------ | --------- | --------------------------- |
| Data should NEVER change       | **Tuple** | safer, immutable            |
| Faster read operations         | **Tuple** | tuples are slightly faster  |
| Store related items (x,y,z)    | **Tuple** | acts like a fixed record    |
| You need to modify data        | **List**  | lists are mutable           |
| Many insert/delete operations  | **List**  | better performance          |
| Passing constant config values | **Tuple** | prevents accidental editing |

### Simple Rule:

* **Use LIST when you want to edit.**
* **Use TUPLE when data is fixed.**

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
