# 🐍 Python Complete Reference Guide
### Beginner to Super Advanced — A to Z Documentation
> *Every concept explained with code examples, real-world usage, and best practices*

---

## Table of Contents

1. [Introduction to Python](#1-introduction-to-python)
2. [Installation & Setup](#2-installation--setup)
3. [Variables & Data Types](#3-variables--data-types)
4. [Operators](#4-operators)
5. [Strings & String Methods](#5-strings--string-methods)
6. [Control Flow — if / elif / else](#6-control-flow--if--elif--else)
7. [Loops — for & while](#7-loops--for--while)
8. [Functions](#8-functions)
9. [Lists](#9-lists)
10. [Tuples](#10-tuples)
11. [Dictionaries](#11-dictionaries)
12. [Sets](#12-sets)
13. [File Handling](#13-file-handling)
14. [Exception Handling](#14-exception-handling)
15. [Modules & Packages](#15-modules--packages)
16. [Object-Oriented Programming (OOP)](#16-object-oriented-programming-oop)
17. [Iterators & Generators](#17-iterators--generators)
18. [Decorators](#18-decorators)
19. [Context Managers](#19-context-managers)
20. [Comprehensions](#20-comprehensions)
21. [Lambda & Functional Programming](#21-lambda--functional-programming)
22. [Regular Expressions](#22-regular-expressions)
23. [Date & Time](#23-date--time)
24. [Math & Random](#24-math--random)
25. [Collections Module](#25-collections-module)
26. [Itertools & Functools](#26-itertools--functools)
27. [Typing & Type Hints](#27-typing--type-hints)
28. [Concurrency — Threading & Asyncio](#28-concurrency--threading--asyncio)
29. [Multiprocessing](#29-multiprocessing)
30. [Networking & HTTP](#30-networking--http)
31. [Working with JSON, CSV & XML](#31-working-with-json-csv--xml)
32. [Databases — SQLite & SQLAlchemy](#32-databases--sqlite--sqlalchemy)
33. [Testing — unittest & pytest](#33-testing--unittest--pytest)
34. [Debugging & Profiling](#34-debugging--profiling)
35. [Virtual Environments & pip](#35-virtual-environments--pip)
36. [Advanced Python Patterns](#36-advanced-python-patterns)
37. [Memory Management & GC](#37-memory-management--garbage-collection)
38. [Metaclasses & Descriptors](#38-metaclasses--descriptors)
39. [C Extensions & ctypes](#39-c-extensions--ctypes)
40. [Best Practices & Style Guide](#40-best-practices--style-guide)

---

## 1. Introduction to Python

Python is a high-level, interpreted, general-purpose programming language created by **Guido van Rossum** and first released in **1991**. Its design philosophy emphasises code readability with the use of significant indentation. Python is dynamically typed, garbage-collected, and supports multiple programming paradigms including structured, object-oriented, and functional programming.

### Why Python?

- ✅ Readable, clean syntax — almost like pseudocode
- ✅ Huge standard library + massive ecosystem (PyPI has 500k+ packages)
- ✅ Cross-platform: Windows, macOS, Linux
- ✅ Used in web development, data science, AI/ML, automation, scripting, and more
- ✅ Strong community and world-class documentation

### Python Versions

Always use **Python 3.x** (Python 2 reached end-of-life in January 2020). As of 2024, **Python 3.12+** is recommended.

```python
# Check your Python version
python --version    # e.g. Python 3.12.2
python3 --version
```

---

## 2. Installation & Setup

### Installing Python

Download from [python.org/downloads](https://python.org/downloads). On macOS you can also use Homebrew:

```bash
# macOS via Homebrew
brew install python

# Ubuntu/Debian
sudo apt update && sudo apt install python3 python3-pip

# Windows — use the official installer or winget:
winget install Python.Python.3
```

### First Python Program

```python
# hello.py
print("Hello, World!")

# Run it
# python hello.py
# Output: Hello, World!
```

### The REPL (Interactive Shell)

Type `python` or `python3` in your terminal to open the interactive interpreter. Great for quick experiments.

```python
>>> 2 + 2
4
>>> name = "Alice"
>>> print(f"Hello, {name}!")
Hello, Alice!
```

> 💡 **Tip:** Use `ipython` (pip install ipython) for a much richer interactive experience with syntax highlighting and auto-completion.

---

## 3. Variables & Data Types

Python variables are **dynamically typed** — you don't declare a type; Python infers it at runtime. A variable is simply a name that references an object in memory.

### Variable Assignment

```python
x = 10           # int
y = 3.14         # float
name = 'Alice'   # str
flag = True      # bool
data = None      # NoneType

# Multiple assignment
a, b, c = 1, 2, 3

# Swap variables (Pythonic!)
a, b = b, a

# Augmented assignment
x += 5    # x = x + 5
x -= 2    # x = x - 2
x *= 3    # x = x * 3
x //= 2   # x = x // 2

# Check type
print(type(x))   # <class 'int'>
print(type(name))  # <class 'str'>
```

### Core Data Types

```python
# int — arbitrary precision integers
big = 10 ** 100   # a googol — Python handles it!
neg = -42

# float — IEEE 754 double precision
pi = 3.141592653589793
sci = 1.5e-10     # scientific notation

# complex
z = 3 + 4j
print(z.real, z.imag)   # 3.0  4.0
print(abs(z))           # 5.0  (magnitude)

# bool (subclass of int)
print(True + True)      # 2
print(int(False))       # 0

# str
greeting = "Hello"

# bytes
raw = b'\x48\x65\x6c\x6c\x6f'
print(raw.decode())   # Hello

# NoneType
nothing = None
print(nothing is None)  # True
```

### Type Conversion (Casting)

```python
int("42")          # 42
int(3.9)           # 3  (truncates, doesn't round)
float("3.14")      # 3.14
str(100)           # "100"
bool(0)            # False
bool("")           # False
bool("hello")      # True
bool([])           # False
bool([0])          # True  (non-empty list)
list((1, 2, 3))    # [1, 2, 3]
tuple([1, 2, 3])   # (1, 2, 3)
set([1, 1, 2, 3])  # {1, 2, 3}
```

> 💡 **Falsy values in Python:** `None`, `False`, `0`, `0.0`, `""`, `[]`, `{}`, `()`, `set()`

---

## 4. Operators

### Arithmetic Operators

```python
a, b = 10, 3

print(a + b)    # 13    addition
print(a - b)    # 7     subtraction
print(a * b)    # 30    multiplication
print(a / b)    # 3.333...  true division (always float)
print(a // b)   # 3     floor division
print(a % b)    # 1     modulo (remainder)
print(a ** b)   # 1000  exponentiation
print(-a % b)   # 2     (Python modulo follows floor division)
```

### Comparison & Logical Operators

```python
x, y = 5, 10

print(x == y)   # False   equal
print(x != y)   # True    not equal
print(x < y)    # True    less than
print(x > y)    # False   greater than
print(x <= y)   # True    less than or equal
print(x >= y)   # False   greater than or equal

# Logical
print(True and False)   # False
print(True or False)    # True
print(not True)         # False

# Short-circuit evaluation
x = None
result = x or "default"   # "default"  (x is falsy)
name = x and x.upper()    # None  (x is falsy, short-circuits)

# Chained comparisons (unique to Python!)
print(1 < 2 < 3)    # True  (equivalent to: 1<2 and 2<3)
print(1 < 2 > 0)    # True
print(0 < x < 10)   # range check in one expression
```

### Bitwise, Identity & Membership Operators

```python
# Bitwise
print(5 & 3)    # 1   AND  (0101 & 0011 = 0001)
print(5 | 3)    # 7   OR   (0101 | 0011 = 0111)
print(5 ^ 3)    # 6   XOR  (0101 ^ 0011 = 0110)
print(~5)       # -6  NOT  (inverts all bits)
print(5 << 1)   # 10  left shift  (multiply by 2)
print(5 >> 1)   # 2   right shift (divide by 2)

# Identity — checks if same object in memory
a = [1, 2]
b = a
c = [1, 2]
print(a is b)       # True  (same object)
print(a is c)       # False (equal but different objects)
print(a is not c)   # True

# Membership
print(2 in [1, 2, 3])     # True
print(5 not in [1, 2, 3]) # True
print("lo" in "hello")    # True
print("key" in {"key": 1})  # True (checks dict keys)
```

---

## 5. Strings & String Methods

Strings in Python are **immutable sequences** of Unicode characters. They are one of the most feature-rich built-in types.

### Creating Strings

```python
s1 = "Hello"
s2 = 'World'
s3 = """Multi
line
string"""

# Raw string (backslashes are literal)
path = r"C:\Users\Alice\file.txt"

# f-string (Python 3.6+) — most recommended
name = "Alice"
age = 30
print(f"My name is {name} and I am {age} years old.")

# f-string with expressions and formatting
print(f"2 + 2 = {2+2}")
print(f"Pi is approximately {3.14159:.2f}")      # 3.14
print(f"{'hello':>10}")                           # right-align
print(f"{1000000:,}")                             # 1,000,000
print(f"{0.856:.1%}")                             # 85.6%

# Python 3.12+ — f-string debug
x = 42
print(f"{x=}")   # x=42
```

### Common String Methods

```python
s = "  Hello, World!  "

# Whitespace
print(s.strip())           # 'Hello, World!'
print(s.lstrip())          # 'Hello, World!  '
print(s.rstrip())          # '  Hello, World!'

# Case
print(s.lower())           # '  hello, world!  '
print(s.upper())           # '  HELLO, WORLD!  '
print(s.title())           # '  Hello, World!  '
print(s.swapcase())        # '  hELLO, wORLD!  '

# Search & Replace
print(s.replace("World", "Python"))
print("hello world".find("world"))     # 6  (-1 if not found)
print("hello world".rfind("l"))        # 9  (search from right)
print("hello world".index("world"))    # 6  (raises ValueError if not found)
print("hello world".count("l"))        # 3

# Split & Join
print("a,b,c".split(","))             # ['a', 'b', 'c']
print("hello world".split())          # ['hello', 'world']  (any whitespace)
print("hello world".split(" ", 1))    # ['hello', 'world']  (max 1 split)
print(", ".join(["a", "b", "c"]))     # 'a, b, c'

# Check content
print("hello".startswith("he"))    # True
print("hello".endswith("lo"))      # True
print("123".isdigit())             # True
print("abc".isalpha())             # True
print("abc123".isalnum())          # True
print("  ".isspace())              # True

# Pad & Align
print("42".zfill(5))              # '00042'
print("hi".center(10, "-"))       # '----hi----'
print("hi".ljust(10, "."))        # 'hi........'
print("hi".rjust(10, "."))        # '........hi'
```

### String Slicing

```python
s = "Python"

print(s[0])      # 'P'    first character
print(s[-1])     # 'n'    last character
print(s[1:4])    # 'yth'  index 1 up to (not including) 4
print(s[:3])     # 'Pyt'  from start to index 3
print(s[3:])     # 'hon'  from index 3 to end
print(s[::2])    # 'Pto'  every 2nd character
print(s[::-1])   # 'nohtyP'  reverse!
print(s[1:-1])   # 'ytho'  exclude first and last
```

---

## 6. Control Flow — if / elif / else

```python
score = 85

if score >= 90:
    grade = "A"
elif score >= 80:
    grade = "B"
elif score >= 70:
    grade = "C"
else:
    grade = "F"

print(f"Grade: {grade}")   # Grade: B
```

### Ternary (Conditional) Expression

```python
age = 20
status = "adult" if age >= 18 else "minor"
print(status)   # adult

# Nested ternary (use sparingly — hurts readability)
label = "high" if x > 100 else ("medium" if x > 50 else "low")
```

### Match Statement (Python 3.10+)

```python
command = "quit"

match command:
    case "quit":
        print("Quitting...")
    case "hello":
        print("Hello!")
    case _:
        print(f"Unknown: {command}")

# Structural pattern matching — powerful!
point = (1, 0)
match point:
    case (0, 0):
        print("Origin")
    case (x, 0):
        print(f"On x-axis at {x}")
    case (0, y):
        print(f"On y-axis at {y}")
    case (x, y):
        print(f"Point at ({x},{y})")

# Match with guards
match value:
    case int(n) if n > 0:
        print("Positive integer")
    case int(n) if n < 0:
        print("Negative integer")
    case _:
        print("Zero or non-integer")
```

---

## 7. Loops — for & while

### for Loop

```python
# Iterate over a list
fruits = ['apple', 'banana', 'cherry']
for fruit in fruits:
    print(fruit)

# range()
for i in range(5):           # 0 1 2 3 4
    print(i, end=' ')

for i in range(2, 10, 2):    # 2 4 6 8  (start, stop, step)
    print(i, end=' ')

for i in range(10, 0, -1):   # 10 9 8 ... 1 (countdown)
    print(i, end=' ')

# enumerate — index + value
for idx, val in enumerate(['a', 'b', 'c']):
    print(idx, val)
# 0 a
# 1 b
# 2 c

# enumerate with custom start
for idx, val in enumerate(['a', 'b', 'c'], start=1):
    print(idx, val)   # 1 a, 2 b, 3 c

# zip — iterate two lists in parallel
names = ['Alice', 'Bob', 'Carol']
ages  = [30, 25, 35]
for name, age in zip(names, ages):
    print(f"{name} is {age}")

# zip with unequal lengths: stops at shortest
# Use itertools.zip_longest to pad with a fill value

# Unpack nested
matrix = [(1, 2), (3, 4), (5, 6)]
for x, y in matrix:
    print(x, y)
```

### while Loop

```python
n = 1
while n <= 5:
    print(n)
    n += 1

# break & continue
for i in range(10):
    if i == 3:
        continue   # skip 3, jump to next iteration
    if i == 7:
        break      # stop the loop entirely
    print(i, end=' ')
# Output: 0 1 2 4 5 6

# while with break
import random
while True:
    n = random.randint(1, 10)
    print(n)
    if n == 5:
        break

# else clause on loop
# The else block runs only if the loop completed WITHOUT a break
for n in range(2, 10):
    for x in range(2, n):
        if n % x == 0:
            break
    else:
        print(n, "is prime")
# 2 is prime, 3 is prime, 5 is prime, 7 is prime
```

---

## 8. Functions

Functions are **first-class objects** in Python — they can be assigned to variables, passed as arguments, and returned from other functions.

### Defining & Calling Functions

```python
def greet(name):
    """Greet a person by name.
    
    Args:
        name: The person's name.
    
    Returns:
        A greeting string.
    """
    return f"Hello, {name}!"

print(greet("Alice"))   # Hello, Alice!

# Function with no return value returns None
def say_hello():
    print("Hello!")

result = say_hello()
print(result)   # None
```

### Default & Keyword Arguments

```python
def power(base, exp=2):
    return base ** exp

print(power(3))          # 9   (uses default exp=2)
print(power(2, 10))      # 1024
print(power(exp=3, base=4))   # 64 (keyword args can be in any order)

# IMPORTANT: Default values are evaluated ONCE at definition time
def append_to(item, lst=[]):   # DANGEROUS — shared mutable default!
    lst.append(item)
    return lst

# Better pattern:
def append_to(item, lst=None):
    if lst is None:
        lst = []
    lst.append(item)
    return lst
```

### `*args` and `**kwargs`

```python
# *args — captures extra positional arguments as a tuple
def total(*args):
    return sum(args)

print(total(1, 2, 3, 4))   # 10

# **kwargs — captures extra keyword arguments as a dict
def display(**kwargs):
    for k, v in kwargs.items():
        print(f"{k} = {v}")

display(name="Alice", age=30)
# name = Alice
# age = 30

# Combining all parameter types
def mixed(a, b, *args, key=None, **kwargs):
    print(a, b, args, key, kwargs)

mixed(1, 2, 3, 4, key='x', extra=True)
# 1 2 (3, 4) x {'extra': True}

# Unpacking into function call
def add(x, y, z):
    return x + y + z

nums = [1, 2, 3]
print(add(*nums))          # 6  (unpack list)

config = {'x': 1, 'y': 2, 'z': 3}
print(add(**config))       # 6  (unpack dict)
```

### Scope — LEGB Rule

Python searches for names in this order: **L**ocal → **E**nclosing → **G**lobal → **B**uilt-in

```python
x = 'global'

def outer():
    x = 'enclosing'
    
    def inner():
        x = 'local'
        print(x)   # local
    
    inner()
    print(x)       # enclosing

outer()
print(x)           # global

# global keyword — modify a global variable from inside a function
count = 0
def increment():
    global count
    count += 1

# nonlocal keyword — modify an enclosing variable
def make_counter():
    n = 0
    def counter():
        nonlocal n
        n += 1
        return n
    return counter

c = make_counter()
print(c())   # 1
print(c())   # 2
print(c())   # 3
```

### Recursion

```python
def factorial(n):
    if n <= 1:
        return 1
    return n * factorial(n - 1)

print(factorial(5))   # 120
print(factorial(0))   # 1

# Fibonacci with memoization (caching)
from functools import lru_cache

@lru_cache(maxsize=None)
def fib(n):
    if n < 2:
        return n
    return fib(n-1) + fib(n-2)

print(fib(50))   # 12586269025 (instant!)
print(fib.cache_info())   # shows hits/misses
```

---

## 9. Lists

Lists are **mutable, ordered sequences**. They are one of the most commonly used data structures in Python.

```python
# Creation
nums = [1, 2, 3, 4, 5]
mixed = [1, 'two', 3.0, True, None]
nested = [[1, 2], [3, 4], [5, 6]]
empty = []

# Access & slice
print(nums[0])      # 1    first element
print(nums[-1])     # 5    last element
print(nums[-2])     # 4    second to last
print(nums[1:3])    # [2, 3]
print(nums[::-1])   # [5, 4, 3, 2, 1]  reversed

# Mutate
nums.append(6)              # add to end: [1,2,3,4,5,6]
nums.insert(0, 0)           # insert at index: [0,1,2,3,4,5,6]
nums.extend([7, 8])         # add multiple items: [0,1,...,8]
nums.remove(3)              # removes FIRST occurrence of value
popped = nums.pop()         # removes & returns last element
nums.pop(0)                 # removes at index 0
del nums[0]                 # delete by index
del nums[1:3]               # delete a slice

# Search
print(3 in nums)            # True/False
print(nums.index(4))        # index of first occurrence
print(nums.count(2))        # number of occurrences

# Sort
nums.sort()                             # in-place ascending
nums.sort(reverse=True)                 # in-place descending
sorted_copy = sorted(nums)              # returns NEW list, original unchanged
sorted_copy = sorted(nums, reverse=True)

# Sort by custom key
words = ['banana', 'apple', 'cherry', 'date']
words.sort(key=len)                    # sort by string length
words.sort(key=lambda w: w[-1])        # sort by last letter
words.sort(key=str.lower)              # case-insensitive sort

# Copy (shallow)
a = [1, 2, [3, 4]]
b = a.copy()         # or: b = a[:]  or: b = list(a)
b[0] = 99
print(a[0])          # 1    (outer list unchanged)
b[2][0] = 99
print(a[2][0])       # 99   (inner list IS shared — shallow copy!)

# Deep copy
import copy
c = copy.deepcopy(a)  # fully independent copy

# List operations
print([1, 2] + [3, 4])   # [1, 2, 3, 4]  concatenation
print([0] * 5)            # [0, 0, 0, 0, 0]  repetition
print(len(nums))           # length
print(min(nums), max(nums), sum(nums))

# Flatten nested list
nested = [[1, 2], [3, 4], [5, 6]]
flat = [x for sublist in nested for x in sublist]
# [1, 2, 3, 4, 5, 6]
```

---

## 10. Tuples

Tuples are **immutable ordered sequences**. Use them for data that should not change — coordinates, RGB colors, database rows, function return values, etc.

```python
# Creation
point = (3, 4)
single = (42,)       # trailing comma required for single-element tuple!
empty  = ()
no_parens = 1, 2, 3  # parentheses optional

# Access & slice (same as list)
print(point[0])      # 3
print(point[-1])     # 4
print(point[0:1])    # (3,)

# Packing & unpacking
x, y = point
print(x, y)   # 3  4

# Extended unpacking
first, *rest = (1, 2, 3, 4, 5)
print(first)   # 1
print(rest)    # [2, 3, 4, 5]

*init, last = (1, 2, 3, 4, 5)
print(last)    # 5

# Swap variables elegantly
a, b = 1, 2
a, b = b, a    # a=2, b=1

# Named tuple — gives fields meaningful names
from collections import namedtuple

Color = namedtuple('Color', ['red', 'green', 'blue'])
red = Color(255, 0, 0)
print(red.red)            # 255
print(red[0])             # 255  (still indexable)
print(red._asdict())      # {'red': 255, 'green': 0, 'blue': 0}
red_brighter = red._replace(red=200)   # returns new tuple

# Tuples as dict keys (lists cannot be)
locations = {(40.7128, -74.0060): "New York", (51.5074, -0.1278): "London"}
```

---

## 11. Dictionaries

Dictionaries are **mutable key-value mappings**. In Python 3.7+, they **preserve insertion order**. Keys must be hashable (immutable).

```python
# Creation
person = {'name': 'Alice', 'age': 30, 'city': 'NYC'}
empty = {}
from_keys = dict.fromkeys(['a', 'b', 'c'], 0)   # {'a':0,'b':0,'c':0}

# Access
print(person['name'])               # Alice (raises KeyError if missing)
print(person.get('age'))            # 30
print(person.get('phone', 'N/A'))   # N/A  (default if missing)

# Mutate
person['email'] = 'alice@example.com'   # add new key
person['age'] = 31                       # update existing key
del person['city']                       # delete key
popped = person.pop('email')             # remove & return value
person.pop('missing', None)              # safe pop with default

# Iteration
for key in person:                  # iterate keys (default)
    print(key)

for k, v in person.items():         # iterate key-value pairs
    print(k, '->', v)

print(list(person.keys()))          # ['name', 'age']
print(list(person.values()))        # ['Alice', 31]

# Check membership
print('name' in person)            # True  (checks keys)
print('Alice' in person.values())  # True

# Merge dictionaries
d1 = {'a': 1, 'b': 2}
d2 = {'b': 3, 'c': 4}

merged = {**d1, **d2}    # {'a':1, 'b':3, 'c':4}  d2 wins
merged = d1 | d2         # Python 3.9+  (same result)
d1 |= d2                 # Python 3.9+  in-place merge

# setdefault — set only if key is missing
person.setdefault('score', 100)   # sets 'score' to 100 only if absent

# defaultdict — auto-creates missing keys
from collections import defaultdict
word_count = defaultdict(int)       # missing key defaults to 0
for word in 'the cat sat on the mat the cat'.split():
    word_count[word] += 1
print(dict(word_count))

graph = defaultdict(list)           # missing key defaults to []
graph['a'].append('b')
graph['a'].append('c')
```

---

## 12. Sets

Sets are **unordered collections of unique, hashable elements**. Ideal for membership tests, deduplication, and mathematical set operations.

```python
# Creation
s = {1, 2, 3, 3, 2}
print(s)              # {1, 2, 3}  — duplicates removed
empty_set = set()     # NOT {}  — that creates an empty dict!
from_list = set([1, 2, 2, 3])

# Operations
s.add(4)              # add one element
s.update([5, 6])      # add multiple elements
s.discard(10)         # remove, no error if missing
s.remove(1)           # remove, raises KeyError if missing
popped = s.pop()      # remove & return arbitrary element

# Set math
a = {1, 2, 3, 4}
b = {3, 4, 5, 6}

print(a | b)          # union:              {1,2,3,4,5,6}
print(a & b)          # intersection:       {3,4}
print(a - b)          # difference:         {1,2}
print(b - a)          # difference:         {5,6}
print(a ^ b)          # symmetric diff:     {1,2,5,6}

# In-place
a |= b                # a = a | b
a &= b                # a = a & b
a -= b                # a = a - b

# Subset / superset
print({1, 2} <= {1, 2, 3})    # True  (subset)
print({1, 2} < {1, 2, 3})     # True  (proper subset)
print({1, 2, 3} >= {1, 2})    # True  (superset)
print({1, 2, 3}.issuperset({1, 2}))   # True

# Frozenset — immutable set (can be used as dict key)
fs = frozenset([1, 2, 3])
d = {fs: "value"}    # valid!
```

---

## 13. File Handling

```python
# Writing to a file
with open('data.txt', 'w') as f:
    f.write("Line 1\n")
    f.write("Line 2\n")

# Reading a file
with open('data.txt', 'r') as f:
    content = f.read()          # read entire file as string

with open('data.txt', 'r') as f:
    lines = f.readlines()       # list of lines (includes \n)

with open('data.txt', 'r') as f:
    line = f.readline()         # read one line at a time

# Reading line by line (memory efficient for large files)
with open('data.txt', 'r') as f:
    for line in f:
        print(line.strip())

# Append to file
with open('data.txt', 'a') as f:
    f.write("Line 3\n")

# Binary files
with open('image.png', 'rb') as f:
    data = f.read()

with open('copy.png', 'wb') as f:
    f.write(data)

# File modes
# 'r'   read (default)
# 'w'   write (creates or truncates)
# 'a'   append
# 'x'   exclusive creation (fails if exists)
# 'r+'  read and write
# 'b'   binary mode (combine with r/w/a)
# 't'   text mode (default)

# Encoding
with open('data.txt', 'r', encoding='utf-8') as f:
    content = f.read()

# File pointer
with open('data.txt', 'r') as f:
    f.seek(0)           # move to beginning
    f.seek(0, 2)        # move to end
    pos = f.tell()      # current position

# os module
import os
os.path.exists('data.txt')       # True/False
os.path.isfile('data.txt')       # is it a file?
os.path.isdir('mydir')           # is it a directory?
os.path.getsize('data.txt')      # size in bytes
os.path.basename('/home/user/file.txt')  # 'file.txt'
os.path.dirname('/home/user/file.txt')   # '/home/user'
os.path.join('home', 'user', 'file')     # 'home/user/file'
os.listdir('.')                  # list directory contents
os.makedirs('a/b/c', exist_ok=True)      # create nested dirs
os.rename('old.txt', 'new.txt')
os.remove('file.txt')

# pathlib — modern, object-oriented (recommended)
from pathlib import Path

p = Path('data.txt')
print(p.read_text())               # read entire file
p.write_text('Hello pathlib!')     # write entire file
print(p.read_bytes())              # read as bytes

print(p.name)        # 'data.txt'
print(p.stem)        # 'data'
print(p.suffix)      # '.txt'
print(p.parent)      # Path('.')
print(p.stat().st_size)   # file size

# Path operations
home = Path.home()
config = home / '.config' / 'app' / 'settings.json'  # / operator!

# Glob
txt_files = list(Path('.').glob('*.txt'))
all_py    = list(Path('.').rglob('**/*.py'))   # recursive

# Create & delete
Path('newdir').mkdir(parents=True, exist_ok=True)
p.unlink()   # delete file
```

---

## 14. Exception Handling

```python
# Basic try/except
try:
    result = 10 / 0
except ZeroDivisionError as e:
    print(f"Error: {e}")   # Error: division by zero

# Multiple exception types
try:
    x = int("abc")
except (ValueError, TypeError) as e:
    print(f"Conversion error: {e}")

# Full try/except/else/finally structure
try:
    f = open("file.txt")
    data = f.read()
except FileNotFoundError:
    print("File not found")
except PermissionError:
    print("Permission denied")
except Exception as e:         # catch-all (use sparingly)
    print(f"Unexpected: {e}")
else:
    print(f"File read: {len(data)} chars")   # only if no exception
finally:
    print("This ALWAYS runs")   # cleanup code goes here

# Raise exceptions
def divide(a, b):
    if b == 0:
        raise ValueError("Denominator cannot be zero")
    return a / b

# Re-raise
try:
    divide(1, 0)
except ValueError:
    print("Caught it, re-raising...")
    raise   # re-raises the same exception

# Exception chaining
try:
    int("abc")
except ValueError as e:
    raise RuntimeError("Processing failed") from e
# Shows both exceptions in traceback

# Custom exceptions
class InsufficientFundsError(Exception):
    def __init__(self, amount, balance):
        self.amount = amount
        self.balance = balance
        super().__init__(
            f"Cannot withdraw ${amount:.2f}, balance is ${balance:.2f}"
        )

class NetworkError(Exception):
    pass

class TimeoutError(NetworkError):   # hierarchy
    pass

# Usage
try:
    raise InsufficientFundsError(100, 50)
except InsufficientFundsError as e:
    print(e.amount, e.balance)

# Exception groups (Python 3.11+)
try:
    raise ExceptionGroup("multiple errors", [
        ValueError("bad value"),
        TypeError("wrong type"),
    ])
except* ValueError as eg:
    print("Handling value errors:", eg.exceptions)
except* TypeError as eg:
    print("Handling type errors:", eg.exceptions)
```

---

## 15. Modules & Packages

```python
# Import a module
import math
print(math.sqrt(16))    # 4.0
print(math.pi)          # 3.141592653589793

# Import specific names
from math import sqrt, pi, factorial
print(sqrt(25))         # 5.0

# Import with alias
import numpy as np           # convention
import pandas as pd
import matplotlib.pyplot as plt

# Import all (avoid in production code)
from math import *

# __name__ guard — code only runs when script is executed directly
if __name__ == "__main__":
    print("Run directly, not imported")

# Package structure
# mypackage/
#   __init__.py          ← makes it a package
#   utils.py
#   models.py
#   api/
#       __init__.py
#       endpoints.py

# Relative imports (inside a package)
from . import utils            # sibling module
from .models import User       # specific name from sibling
from ..common import helpers   # parent package

# Useful standard library modules
import os, sys, re, json, csv
import datetime, time, random
import collections, itertools, functools
import pathlib, shutil, glob
import threading, multiprocessing, asyncio
import urllib.request, http.server
import sqlite3, pickle, hashlib, base64
import argparse, logging, configparser

# sys — system info
import sys
print(sys.version)          # Python version string
print(sys.platform)         # 'linux', 'darwin', 'win32'
print(sys.argv)             # command-line arguments
sys.exit(0)                 # exit the program
sys.path.append('/my/path') # add to module search path
```

---

## 16. Object-Oriented Programming (OOP)

### Classes & Objects

```python
class Animal:
    species = "Unknown"     # class variable — shared by all instances

    def __init__(self, name, sound):
        self.name = name    # instance variable — unique to each instance
        self.sound = sound

    def speak(self):
        return f"{self.name} says {self.sound}!"

    def __repr__(self):     # unambiguous representation (for developers)
        return f"Animal(name={self.name!r}, sound={self.sound!r})"

    def __str__(self):      # readable representation (for users)
        return self.name

    def __len__(self):
        return len(self.name)

dog = Animal("Rex", "Woof")
print(dog.speak())   # Rex says Woof!
print(repr(dog))     # Animal(name='Rex', sound='Woof')
print(str(dog))      # Rex
print(len(dog))      # 3
```

### Inheritance

```python
class Dog(Animal):
    def __init__(self, name, breed):
        super().__init__(name, "Woof")   # call parent __init__
        self.breed = breed

    def fetch(self, item):
        return f"{self.name} fetches the {item}"

    def speak(self):    # METHOD OVERRIDE
        return f"Woof! I am {self.name}, a {self.breed}."

rex = Dog("Rex", "Labrador")
print(rex.speak())          # Woof! I am Rex, a Labrador.
print(rex.fetch("ball"))    # Rex fetches the ball
print(isinstance(rex, Dog))     # True
print(isinstance(rex, Animal))  # True  (is-a relationship)
print(issubclass(Dog, Animal))  # True

# Multiple Inheritance
class Flyable:
    def fly(self):
        return f"{self.name} is flying!"

class FlyingDog(Dog, Flyable):
    pass

fido = FlyingDog("Fido", "Poodle")
print(fido.fly())   # Fido is flying!

# MRO — Method Resolution Order
print(FlyingDog.__mro__)
```

### Encapsulation & Properties

```python
class BankAccount:
    def __init__(self, owner, balance=0):
        self.owner = owner
        self._balance = balance       # 'protected' (convention)
        self.__id = id(self)          # 'private' (name-mangled)

    @property
    def balance(self):
        return self._balance

    @balance.setter
    def balance(self, value):
        if value < 0:
            raise ValueError("Balance cannot be negative")
        self._balance = value

    @balance.deleter
    def balance(self):
        self._balance = 0

    def deposit(self, amount):
        if amount <= 0:
            raise ValueError("Deposit must be positive")
        self._balance += amount
        return self

    def withdraw(self, amount):
        if amount > self._balance:
            raise ValueError("Insufficient funds")
        self._balance -= amount
        return self   # enables method chaining

    def __repr__(self):
        return f"BankAccount({self.owner!r}, balance={self._balance})"

acc = BankAccount("Alice", 100)
acc.balance = 200       # uses setter
print(acc.balance)      # 200  (uses getter)
acc.deposit(50).withdraw(30)   # method chaining
```

### Dunder (Magic) Methods

```python
class Vector:
    def __init__(self, x, y):
        self.x, self.y = x, y

    # Arithmetic
    def __add__(self, other):   return Vector(self.x+other.x, self.y+other.y)
    def __sub__(self, other):   return Vector(self.x-other.x, self.y-other.y)
    def __mul__(self, scalar):  return Vector(self.x*scalar, self.y*scalar)
    def __rmul__(self, scalar): return self.__mul__(scalar)  # 3 * v
    def __neg__(self):          return Vector(-self.x, -self.y)

    # Comparison
    def __eq__(self, other):    return self.x == other.x and self.y == other.y
    def __lt__(self, other):    return abs(self) < abs(other)
    def __abs__(self):          return (self.x**2 + self.y**2)**0.5

    # Container protocol
    def __len__(self):          return 2
    def __getitem__(self, i):   return (self.x, self.y)[i]
    def __iter__(self):         return iter((self.x, self.y))

    # String
    def __repr__(self):         return f"Vector({self.x}, {self.y})"

    # Boolean
    def __bool__(self):         return self.x != 0 or self.y != 0

v1 = Vector(1, 2)
v2 = Vector(3, 4)
print(v1 + v2)      # Vector(4, 6)
print(3 * v1)       # Vector(3, 6)
print(abs(v2))      # 5.0
x, y = v1           # unpacking via __iter__
```

### Class Methods, Static Methods & Dataclasses

```python
class Pizza:
    _count = 0

    def __init__(self, toppings):
        self.toppings = toppings
        Pizza._count += 1

    @classmethod
    def margherita(cls):            # factory method — returns instance
        return cls(['tomato', 'mozzarella'])

    @classmethod
    def total_pizzas(cls):
        return cls._count

    @staticmethod
    def validate_topping(t):        # utility — doesn't need self or cls
        return isinstance(t, str) and t.isalpha()

    def __repr__(self):
        return f"Pizza({self.toppings})"

p = Pizza.margherita()
print(p)                        # Pizza(['tomato', 'mozzarella'])
print(Pizza.validate_topping("cheese"))   # True
print(Pizza.total_pizzas())     # 1

# dataclass — auto-generates __init__, __repr__, __eq__, etc.
from dataclasses import dataclass, field
from typing import List

@dataclass
class Point:
    x: float
    y: float
    label: str = 'origin'
    tags: List[str] = field(default_factory=list)

    def distance_from_origin(self):
        return (self.x**2 + self.y**2)**0.5

@dataclass(frozen=True)   # immutable (hashable — can use as dict key)
class ImmutablePoint:
    x: float
    y: float

@dataclass(order=True)    # generates __lt__, __le__, etc.
class SortablePoint:
    x: float
    y: float

p = Point(1.0, 2.0, 'A')
print(p)   # Point(x=1.0, y=2.0, label='A', tags=[])
```

---

## 17. Iterators & Generators

### Iterators

Any object with `__iter__()` and `__next__()` methods is an iterator.

```python
class Countdown:
    def __init__(self, n):
        self.n = n

    def __iter__(self):
        return self

    def __next__(self):
        if self.n <= 0:
            raise StopIteration
        self.n -= 1
        return self.n + 1

for x in Countdown(5):
    print(x, end=' ')   # 5 4 3 2 1

# Under the hood, for loops do:
it = iter([1, 2, 3])   # calls __iter__
print(next(it))         # 1  calls __next__
print(next(it))         # 2
print(next(it))         # 3
# next(it)  → StopIteration
```

### Generators

Generator functions use `yield` to produce values lazily — one at a time, only when needed.

```python
# Generator function
def fibonacci():
    a, b = 0, 1
    while True:
        yield a          # pause here, return a
        a, b = b, a + b  # resume here next time

gen = fibonacci()
print([next(gen) for _ in range(8)])
# [0, 1, 1, 2, 3, 5, 8, 13]

# Generators are memory-efficient — infinite sequence, no memory issue!

# Generator with finite sequence
def range_squared(n):
    for i in range(n):
        yield i ** 2

for sq in range_squared(5):
    print(sq, end=' ')   # 0 1 4 9 16

# Generator expression (like list comp, but lazy)
squares = (x**2 for x in range(1000000))   # no list created!
print(sum(squares))   # processes one at a time

# yield from — delegate to sub-generator
def chain(*iterables):
    for it in iterables:
        yield from it

print(list(chain([1, 2], [3, 4], [5])))   # [1, 2, 3, 4, 5]

# send() — two-way communication with generator
def accumulator():
    total = 0
    while True:
        value = yield total   # send value in, get total out
        if value is None:
            break
        total += value

acc = accumulator()
next(acc)             # prime the generator (advance to first yield)
print(acc.send(10))   # 10
print(acc.send(20))   # 30
print(acc.send(5))    # 35
```

---

## 18. Decorators

Decorators modify or enhance functions/classes without permanently modifying their source code. They are a form of **metaprogramming**.

```python
import time, functools

# Simple decorator
def timer(func):
    @functools.wraps(func)    # preserve __name__, __doc__, etc.
    def wrapper(*args, **kwargs):
        start = time.perf_counter()
        result = func(*args, **kwargs)
        end = time.perf_counter()
        print(f"{func.__name__} took {end-start:.4f}s")
        return result
    return wrapper

@timer
def slow_function():
    time.sleep(0.1)

slow_function()   # slow_function took 0.1002s

# Decorator with arguments (factory pattern)
def repeat(n):
    def decorator(func):
        @functools.wraps(func)
        def wrapper(*args, **kwargs):
            for _ in range(n):
                result = func(*args, **kwargs)
            return result
        return wrapper
    return decorator

@repeat(3)
def say_hello():
    print("Hello!")

say_hello()   # Hello! Hello! Hello!

# Stacking decorators (applied bottom-up)
@timer
@repeat(2)
def greet(name):
    print(f"Hi {name}")

# Equivalent to: greet = timer(repeat(2)(greet))

# Class-based decorator
class Memoize:
    def __init__(self, func):
        self.func = func
        self.cache = {}
        functools.update_wrapper(self, func)

    def __call__(self, *args):
        if args not in self.cache:
            self.cache[args] = self.func(*args)
        return self.cache[args]

@Memoize
def fib(n):
    return n if n < 2 else fib(n-1) + fib(n-2)

# Practical decorators
def validate_types(**type_map):
    def decorator(func):
        @functools.wraps(func)
        def wrapper(*args, **kwargs):
            import inspect
            sig = inspect.signature(func)
            bound = sig.bind(*args, **kwargs)
            for param, value in bound.arguments.items():
                if param in type_map and not isinstance(value, type_map[param]):
                    raise TypeError(f"{param} must be {type_map[param].__name__}")
            return func(*args, **kwargs)
        return wrapper
    return decorator

@validate_types(name=str, age=int)
def create_user(name, age):
    return {'name': name, 'age': age}
```

---

## 19. Context Managers

Context managers handle resource acquisition and release automatically using the `with` statement.

```python
# Custom context manager via class
import time

class Timer:
    def __enter__(self):
        self.start = time.perf_counter()
        return self

    def __exit__(self, exc_type, exc_val, exc_tb):
        self.elapsed = time.perf_counter() - self.start
        print(f"Elapsed: {self.elapsed:.4f}s")
        return False   # False = don't suppress exceptions
                       # True  = suppress exceptions

with Timer() as t:
    time.sleep(0.05)
# Elapsed: 0.0503s
print(t.elapsed)   # also accessible after the with block

# Using contextlib
from contextlib import contextmanager, suppress

@contextmanager
def managed_resource(name):
    print(f"Acquiring {name}")
    try:
        yield name   # value given to 'as' clause
    except Exception as e:
        print(f"Error during {name}: {e}")
        raise
    finally:
        print(f"Releasing {name}")   # always runs

with managed_resource('database') as r:
    print(f"Using {r}")
# Acquiring database
# Using database
# Releasing database

# suppress — ignore specific exceptions
with suppress(FileNotFoundError):
    os.remove("nonexistent_file.txt")   # silently ignored

# ExitStack — manage dynamic number of context managers
from contextlib import ExitStack

files = ['a.txt', 'b.txt', 'c.txt']
with ExitStack() as stack:
    handles = [stack.enter_context(open(f)) for f in files]
    # all files auto-closed when exiting
```

---

## 20. Comprehensions

```python
# List comprehension — [expression for item in iterable if condition]
squares = [x**2 for x in range(10)]
# [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]

evens = [x for x in range(20) if x % 2 == 0]
# [0, 2, 4, 6, 8, 10, 12, 14, 16, 18]

# With transformation in condition
abs_vals = [abs(x) for x in range(-5, 6)]

# Nested list comprehension (outer loop first)
matrix = [[i*j for j in range(1, 4)] for i in range(1, 4)]
# [[1,2,3], [2,4,6], [3,6,9]]

# Flatten a nested list
nested = [[1, 2, 3], [4, 5], [6, 7, 8]]
flat = [x for row in nested for x in row]
# [1, 2, 3, 4, 5, 6, 7, 8]

# Dict comprehension
squared_dict = {x: x**2 for x in range(6)}
# {0:0, 1:1, 2:4, 3:9, 4:16, 5:25}

# Invert a dict
orig = {'a': 1, 'b': 2, 'c': 3}
inverted = {v: k for k, v in orig.items()}
# {1:'a', 2:'b', 3:'c'}

# Filter a dict
big = {k: v for k, v in orig.items() if v > 1}

# Set comprehension
unique_lens = {len(w) for w in ['hello', 'world', 'hi']}
# {2, 5}

# Generator expression — lazy evaluation, no list created
total = sum(x**2 for x in range(1_000_000))   # memory efficient!

# Walrus operator (:=) in comprehension (Python 3.8+)
import re
results = [m.group() for text in texts if (m := re.search(r'\d+', text))]
```

---

## 21. Lambda & Functional Programming

```python
# lambda — anonymous single-expression function
square = lambda x: x ** 2
print(square(5))   # 25

add = lambda x, y: x + y
print(add(3, 4))   # 7

# Common use: sort with key
data = [{'name': 'Charlie', 'age': 30}, {'name': 'Alice', 'age': 25}]
data.sort(key=lambda d: d['age'])
data.sort(key=lambda d: (d['age'], d['name']))   # multi-key sort

# map() — apply function to every element
nums = [1, 2, 3, 4, 5]
squared = list(map(lambda x: x**2, nums))        # [1,4,9,16,25]
doubled = list(map(lambda x: x*2, nums))

# filter() — keep elements where function returns True
evens = list(filter(lambda x: x % 2 == 0, nums))

# reduce() — fold sequence to single value
from functools import reduce
product = reduce(lambda a, b: a * b, nums)        # 120
total   = reduce(lambda a, b: a + b, nums, 0)     # 15 (0 is initial value)

# Prefer comprehensions over map/filter (more readable)
squared = [x**2 for x in nums]              # ✅ cleaner
evens   = [x for x in nums if x % 2 == 0]  # ✅ cleaner

# partial — fix some arguments, creating a new function
from functools import partial

def power(base, exp):
    return base ** exp

square = partial(power, exp=2)
cube   = partial(power, exp=3)
print(square(4))   # 16
print(cube(3))     # 27

# Higher-order functions
def compose(f, g):
    return lambda x: f(g(x))

double = lambda x: x * 2
inc    = lambda x: x + 1
double_then_inc = compose(inc, double)
print(double_then_inc(5))   # 11

# Functions as first-class objects
operations = {
    'add': lambda a, b: a + b,
    'sub': lambda a, b: a - b,
    'mul': lambda a, b: a * b,
}
print(operations['add'](3, 4))   # 7
```

---

## 22. Regular Expressions

```python
import re

text = "Contact us at support@example.com or info@test.org"

# re.search — find first match anywhere in string
match = re.search(r'[\w.-]+@[\w.-]+\.\w+', text)
if match:
    print(match.group())    # support@example.com
    print(match.start())    # start position
    print(match.end())      # end position
    print(match.span())     # (start, end) tuple

# re.match — match only at beginning of string
m = re.match(r'\d+', '123abc')
print(m.group())   # '123'

# re.fullmatch — entire string must match
m = re.fullmatch(r'\d+', '123')   # matches
m = re.fullmatch(r'\d+', '123abc')   # None

# re.findall — return all matches as list
emails = re.findall(r'[\w.-]+@[\w.-]+\.\w+', text)
print(emails)   # ['support@example.com', 'info@test.org']

# re.finditer — return all matches as iterator of match objects
for m in re.finditer(r'\w+@\w+\.\w+', text):
    print(m.group(), m.start())

# re.sub — substitute matches
censored = re.sub(r'[\w.-]+@[\w.-]+\.\w+', '[REDACTED]', text)
# Count replacements
new_text, n = re.subn(r'\d', '#', 'abc123def456')   # n=6

# re.split — split on pattern
parts = re.split(r'[\s,;]+', "one two,three;four")
# ['one', 'two', 'three', 'four']

# Compile for reuse (better performance)
EMAIL_RE = re.compile(r'[\w.-]+@[\w.-]+\.\w+', re.IGNORECASE)
matches = EMAIL_RE.findall(text)

# Groups
date_str = '2024-07-15'
m = re.match(r'(\d{4})-(\d{2})-(\d{2})', date_str)
print(m.groups())      # ('2024', '07', '15')
print(m.group(0))      # '2024-07-15'  (full match)
print(m.group(1))      # '2024'
print(m.group(1, 3))   # ('2024', '15')

# Named groups — much more readable!
m = re.match(r'(?P<year>\d{4})-(?P<month>\d{2})-(?P<day>\d{2})', date_str)
print(m.group('year'))    # '2024'
print(m.groupdict())      # {'year': '2024', 'month': '07', 'day': '15'}

# Lookahead & lookbehind
prices = re.findall(r'\d+(?=\$)', '100$ 200$ hello 50')   # before $
prices = re.findall(r'(?<=\$)\d+', '$100 $200 hello $50') # after $

# Flags
re.findall(r'python', text, re.IGNORECASE)   # case-insensitive
re.match(r'^start', text, re.MULTILINE)       # ^ matches each line start
re.search(r'.', text, re.DOTALL)              # . matches newlines too

# Common patterns
PATTERNS = {
    'email':   r'[\w.-]+@[\w.-]+\.\w+',
    'phone':   r'\+?1?\s?\(?\d{3}\)?[\s.-]\d{3}[\s.-]\d{4}',
    'url':     r'https?://[\w/:%#\$&\?\(\)~\.=\+\-]+',
    'ipv4':    r'\b(?:\d{1,3}\.){3}\d{1,3}\b',
    'zip_us':  r'\b\d{5}(?:-\d{4})?\b',
}
```

---

## 23. Date & Time

```python
from datetime import datetime, date, time, timedelta
import time as time_module
from zoneinfo import ZoneInfo   # Python 3.9+

# Current date and time
now   = datetime.now()                        # local time, naive
today = date.today()
print(now)     # 2024-07-15 14:32:01.123456
print(today)   # 2024-07-15

# Create specific datetime
dt     = datetime(2024, 12, 25, 8, 0, 0)
d      = date(2024, 12, 25)
t      = time(8, 30, 0)

# Components
print(now.year, now.month, now.day)
print(now.hour, now.minute, now.second, now.microsecond)
print(now.weekday())   # 0=Monday, 6=Sunday
print(now.isoweekday()) # 1=Monday, 7=Sunday

# Arithmetic with timedelta
one_week   = timedelta(weeks=1)
two_days   = timedelta(days=2, hours=3)
next_week  = today + one_week
yesterday  = today - timedelta(days=1)

# Time until an event
countdown = datetime(2025, 1, 1) - datetime.now()
print(f"Days until 2025: {countdown.days}")
print(f"Total seconds: {countdown.total_seconds():.0f}")

# Formatting — strftime (datetime to string)
print(now.strftime("%Y-%m-%d %H:%M:%S"))    # 2024-07-15 14:32:01
print(now.strftime("%d %B %Y"))             # 15 July 2024
print(now.strftime("%A, %d %b %Y"))         # Monday, 15 Jul 2024
print(now.strftime("%I:%M %p"))             # 02:32 PM
print(now.isoformat())                      # 2024-07-15T14:32:01.123456

# Parsing — strptime (string to datetime)
dt = datetime.strptime("25/12/2024", "%d/%m/%Y")
dt = datetime.strptime("July 15, 2024", "%B %d, %Y")
dt = datetime.fromisoformat("2024-07-15T14:30:00")  # Python 3.7+

# Timezone-aware datetimes
utc_now = datetime.now(ZoneInfo("UTC"))
ny_now  = datetime.now(ZoneInfo("America/New_York"))
ist_now = datetime.now(ZoneInfo("Asia/Kolkata"))

# Convert between timezones
ny_in_utc = ny_now.astimezone(ZoneInfo("UTC"))

# Unix timestamp
timestamp = now.timestamp()
dt_from_ts = datetime.fromtimestamp(timestamp)

# Performance timing
start = time_module.perf_counter()
# ... do work ...
elapsed = time_module.perf_counter() - start

# time.sleep
time_module.sleep(1.5)   # sleep 1.5 seconds
```

---

## 24. Math & Random

```python
import math, random, statistics

# ── math ──────────────────────────────────────────
math.floor(3.7)           # 3    (round down)
math.ceil(3.2)            # 4    (round up)
math.trunc(3.9)           # 3    (towards zero)
round(3.5)                # 4    (banker's rounding)
round(3.14159, 2)         # 3.14

math.sqrt(144)            # 12.0
math.pow(2, 10)           # 1024.0  (float)
2 ** 10                   # 1024    (int, preferred)

math.log(1000, 10)        # 3.0   (log base 10)
math.log(math.e)          # 1.0   (natural log)
math.log2(1024)           # 10.0

math.sin(math.pi/2)       # 1.0
math.cos(0)               # 1.0
math.tan(math.pi/4)       # ~1.0
math.degrees(math.pi)     # 180.0
math.radians(180)         # 3.14159...

math.factorial(10)        # 3628800
math.gcd(12, 18)          # 6
math.lcm(4, 6)            # 12  (Python 3.9+)
math.comb(10, 3)          # 120  (combinations)
math.perm(10, 3)          # 720  (permutations)

math.isclose(0.1+0.2, 0.3)      # True (float comparison!)
math.isclose(0.1+0.2, 0.3, rel_tol=1e-9)

math.inf                  # infinity
math.isinf(math.inf)      # True
math.nan                  # not a number
math.isnan(math.nan)      # True

# ── random ────────────────────────────────────────
random.seed(42)                    # reproducible results
random.random()                    # float 0.0 to 1.0
random.uniform(1.5, 2.5)           # float in range
random.randint(1, 10)              # int, both ends inclusive
random.randrange(0, 100, 5)        # 0,5,10,...,95
random.choice(['a', 'b', 'c'])     # random element
random.choices(['a','b','c'], weights=[1,2,3], k=5)  # weighted
random.sample(range(100), 10)      # 10 unique items (no replacement)

items = [1, 2, 3, 4, 5]
random.shuffle(items)              # in-place shuffle

# Cryptographically secure random
import secrets
secrets.token_hex(16)              # 32-char hex string
secrets.token_urlsafe(16)          # URL-safe base64
secrets.choice(['a', 'b', 'c'])    # secure choice

# ── statistics ────────────────────────────────────
data = [2, 4, 4, 4, 5, 5, 7, 9]

statistics.mean(data)          # 5.0    arithmetic mean
statistics.fmean(data)         # 5.0    fast float mean
statistics.geometric_mean(data) # 4.567 geometric mean
statistics.median(data)        # 4.5    middle value
statistics.median_low(data)    # 4      lower median
statistics.median_high(data)   # 5      upper median
statistics.mode(data)          # 4      most common
statistics.multimode(data)     # [4, 5] if multiple modes

statistics.stdev(data)         # 2.0    sample std deviation
statistics.pstdev(data)        # std deviation of population
statistics.variance(data)      # 4.0    sample variance

statistics.correlation([1,2,3], [2,4,6])   # 1.0  (Python 3.10+)
statistics.linear_regression([1,2,3],[2,4,6])  # LinearRegression(slope=2.0,...)
```

---

## 25. Collections Module

```python
from collections import (Counter, defaultdict, OrderedDict,
                          deque, namedtuple, ChainMap)

# ── Counter ───────────────────────────────────────
words = "the cat sat on the mat the cat".split()
c = Counter(words)
print(c)                     # Counter({'the': 3, 'cat': 2, ...})
print(c.most_common(2))      # [('the',3), ('cat',2)]
print(c['the'])              # 3
print(c['missing'])          # 0  (no KeyError!)

c.update(['the', 'dog'])     # add more counts
c.subtract(['the'])          # subtract counts

# Counter arithmetic
a = Counter({'a': 3, 'b': 2})
b = Counter({'a': 1, 'b': 4, 'c': 1})
print(a + b)   # Counter({'b':6,'a':4,'c':1})
print(a - b)   # Counter({'a':2})  (only positive counts)
print(a & b)   # Counter({'a':1,'b':2}) (minimum)
print(a | b)   # Counter({'b':4,'a':3,'c':1}) (maximum)

# Total count
print(c.total())   # Python 3.10+

# ── defaultdict ───────────────────────────────────
# Grouping
from collections import defaultdict

word_count = defaultdict(int)
for word in words:
    word_count[word] += 1

# Group by first letter
groups = defaultdict(list)
for word in words:
    groups[word[0]].append(word)

nested = defaultdict(lambda: defaultdict(int))   # nested defaultdict

# ── deque ─────────────────────────────────────────
dq = deque([1, 2, 3], maxlen=5)   # maxlen: auto-drops oldest when full
dq.appendleft(0)    # add to left: O(1)
dq.append(4)        # add to right: O(1)
dq.popleft()        # remove from left: O(1)
dq.pop()            # remove from right: O(1)
dq.rotate(1)        # rotate right (negative = rotate left)
dq.extendleft([10, 20])   # extend left (reversed!)

# deque as queue (FIFO)
queue = deque()
queue.append('task1')    # enqueue
queue.append('task2')
queue.popleft()          # dequeue

# deque as stack (LIFO)
stack = deque()
stack.append('item')     # push
stack.pop()              # pop

# ── namedtuple ────────────────────────────────────
Point = namedtuple('Point', ['x', 'y'])
p = Point(3, 4)
print(p.x, p.y)          # 3 4
print(p[0])              # 3  (still indexable)
print(p._asdict())       # {'x': 3, 'y': 4}
p2 = p._replace(x=10)   # returns new namedtuple
print(Point._fields)     # ('x', 'y')

# typed version (Python 3.6+)
from typing import NamedTuple
class Employee(NamedTuple):
    name: str
    department: str
    salary: float = 50000.0

emp = Employee("Alice", "Engineering")
print(emp.name)   # Alice

# ── ChainMap ──────────────────────────────────────
defaults  = {'color': 'red', 'size': 'M', 'debug': False}
overrides = {'color': 'blue', 'debug': True}
env_vars  = {'size': 'L'}

cm = ChainMap(env_vars, overrides, defaults)
print(cm['color'])   # 'blue'  (from overrides)
print(cm['size'])    # 'L'     (from env_vars)
print(cm['debug'])   # True    (from overrides)

# Updates go to first map
cm['new_key'] = 'value'   # added to env_vars
```

---

## 26. Itertools & Functools

```python
import itertools, functools

# ── itertools ─────────────────────────────────────

# chain — combine multiple iterables
list(itertools.chain([1,2],[3,4],[5]))       # [1,2,3,4,5]
list(itertools.chain.from_iterable([[1,2],[3,4]]))  # same

# count — infinite counter
for i in itertools.islice(itertools.count(10, 2), 5):
    print(i)   # 10 12 14 16 18

# cycle — repeat infinitely
colors = itertools.cycle(['red','green','blue'])
print([next(colors) for _ in range(6)])  # repeats...

# repeat — repeat n times
list(itertools.repeat(0, 5))   # [0,0,0,0,0]

# product — Cartesian product
list(itertools.product('AB', repeat=2))
# [('A','A'),('A','B'),('B','A'),('B','B')]

list(itertools.product([1,2], [3,4]))
# [(1,3),(1,4),(2,3),(2,4)]

# permutations & combinations
list(itertools.permutations([1,2,3], 2))
# [(1,2),(1,3),(2,1),(2,3),(3,1),(3,2)]

list(itertools.combinations([1,2,3,4], 2))
# [(1,2),(1,3),(1,4),(2,3),(2,4),(3,4)]

list(itertools.combinations_with_replacement([1,2,3], 2))
# [(1,1),(1,2),(1,3),(2,2),(2,3),(3,3)]

# groupby — group consecutive elements
data = [('M','Alice'),('M','Bob'),('F','Carol'),('F','Dana')]
for gender, group in itertools.groupby(data, key=lambda x: x[0]):
    print(gender, [p[1] for p in group])
# M ['Alice', 'Bob']
# F ['Carol', 'Dana']

# islice — slice any iterable
list(itertools.islice(range(100), 0, 20, 2))   # [0,2,4,...,18]

# accumulate
list(itertools.accumulate([1,2,3,4,5]))
# [1, 3, 6, 10, 15]  (running sum)

import operator
list(itertools.accumulate([1,2,3,4,5], operator.mul))
# [1, 2, 6, 24, 120]  (running product = factorials)

# takewhile / dropwhile
list(itertools.takewhile(lambda x: x<5, [1,2,3,4,5,6]))  # [1,2,3,4]
list(itertools.dropwhile(lambda x: x<5, [1,2,3,4,5,6]))  # [5,6]

# starmap
list(itertools.starmap(pow, [(2,5),(3,2),(10,3)]))  # [32,9,1000]

# ── functools ─────────────────────────────────────

# lru_cache / cache — memoize function results
@functools.lru_cache(maxsize=128)
def expensive(n):
    return sum(range(n))

@functools.cache   # Python 3.9+ — unlimited size
def fib(n):
    return n if n < 2 else fib(n-1) + fib(n-2)

fib.cache_clear()     # clear the cache
fib.cache_info()      # CacheInfo(hits=..., misses=..., maxsize=...)

# reduce
functools.reduce(lambda a,b: a+b, [1,2,3,4,5])    # 15
functools.reduce(lambda a,b: a+b, [], 0)           # 0 (initial value)

# partial
def log(level, message):
    print(f"[{level}] {message}")

info  = functools.partial(log, "INFO")
error = functools.partial(log, "ERROR")
info("Server started")    # [INFO] Server started
error("Disk full!")       # [ERROR] Disk full!

# total_ordering — only implement __eq__ and one of __lt__/__le__/__gt__/__ge__
@functools.total_ordering
class Card:
    RANKS = '23456789TJQKA'
    def __init__(self, rank): self.rank = rank
    def __eq__(self, other):  return self.rank == other.rank
    def __lt__(self, other):  return self.RANKS.index(self.rank) < self.RANKS.index(other.rank)
    # Python auto-generates __le__, __gt__, __ge__

# singledispatch — function overloading by type
@functools.singledispatch
def process(arg):
    print(f"Generic: {arg}")

@process.register(int)
def _(arg):
    print(f"Integer: {arg * 2}")

@process.register(str)
def _(arg):
    print(f"String: {arg.upper()}")

process(42)       # Integer: 84
process("hello")  # String: HELLO
process(3.14)     # Generic: 3.14
```

---

## 27. Typing & Type Hints

```python
# Python 3.5+: PEP 484 type hints (not enforced at runtime — use mypy)

from typing import (List, Dict, Tuple, Set, Optional, Union,
                    Callable, Any, TypeVar, Generic, Iterator,
                    Sequence, Mapping, Iterable, ClassVar)
from typing import TypedDict, Protocol, Literal, Final, Annotated

# Basic annotations
def greet(name: str) -> str:
    return f"Hello, {name}"

def add(a: int, b: int) -> int:
    return a + b

# Container types (Python 3.9+: use built-in list/dict/etc. directly)
def process(items: list[int], factor: float = 1.0) -> list[float]:
    return [x * factor for x in items]

# Optional — can be None
def find(items: list[str], target: str) -> int | None:
    try:
        return items.index(target)
    except ValueError:
        return None

# Union (Python 3.10+ syntax: X | Y)
def parse(value: str | int) -> int:
    return int(value)

# TypeVar for generics
T = TypeVar('T')
K = TypeVar('K')
V = TypeVar('V')

def first(items: list[T]) -> T | None:
    return items[0] if items else None

def get_or_default(d: dict[K, V], key: K, default: V) -> V:
    return d.get(key, default)

# Generic class
class Stack(Generic[T]):
    def __init__(self) -> None:
        self._items: list[T] = []
    
    def push(self, item: T) -> None:
        self._items.append(item)
    
    def pop(self) -> T:
        return self._items.pop()

s: Stack[int] = Stack()
s.push(42)

# Callable
def apply(func: Callable[[int, int], int], a: int, b: int) -> int:
    return func(a, b)

# TypedDict — dict with specific key types
class Movie(TypedDict):
    title: str
    year: int
    rating: float

class PartialMovie(TypedDict, total=False):   # all keys optional
    title: str
    year: int

# Protocol — structural subtyping (duck typing + hints)
class Drawable(Protocol):
    def draw(self) -> None: ...
    def resize(self, factor: float) -> None: ...

def render(shape: Drawable) -> None:
    shape.draw()   # anything with draw() qualifies — no explicit inheritance!

# Literal — specific values only
def set_direction(direction: Literal['north','south','east','west']) -> None:
    ...

# Final — cannot be reassigned
MAX_SIZE: Final = 100

# ClassVar — class-level variable
class MyClass:
    count: ClassVar[int] = 0
    name: str

# Annotated — attach metadata
from typing import Annotated
Positive = Annotated[int, "must be > 0"]

# Type aliases (Python 3.12+)
type Vector = list[float]
type Matrix = list[Vector]

# Running mypy
# pip install mypy
# mypy my_script.py
# mypy --strict my_script.py  (stricter checks)
```

---

## 28. Concurrency — Threading & Asyncio

### Threading

```python
import threading, time, queue

# Basic thread
def worker(name, delay):
    print(f"Thread {name} starting")
    time.sleep(delay)
    print(f"Thread {name} done")

threads = []
for i in range(3):
    t = threading.Thread(target=worker, args=(f"T{i}", i*0.1))
    threads.append(t)
    t.start()

for t in threads:
    t.join()   # wait for all threads to finish

# Thread with return value (via queue)
def compute(n, result_queue):
    result_queue.put(n ** 2)

q = queue.Queue()
t = threading.Thread(target=compute, args=(5, q))
t.start()
t.join()
print(q.get())   # 25

# Thread-safe synchronization
lock = threading.Lock()
counter = 0

def safe_increment():
    global counter
    with lock:       # acquire and release automatically
        counter += 1

# RLock — reentrant lock (same thread can acquire multiple times)
rlock = threading.RLock()

# Semaphore — limit concurrent access
sem = threading.Semaphore(3)   # max 3 threads at once
with sem:
    pass   # critical section

# Event — signal between threads
ready = threading.Event()

def waiter():
    ready.wait()   # block until event is set
    print("Go!")

def setter():
    time.sleep(1)
    ready.set()

# ThreadPoolExecutor — high-level API (recommended)
from concurrent.futures import ThreadPoolExecutor, as_completed

def fetch(url):
    # simulate web request
    time.sleep(0.1)
    return f"Result from {url}"

urls = [f"https://example.com/{i}" for i in range(10)]

with ThreadPoolExecutor(max_workers=5) as executor:
    futures = {executor.submit(fetch, url): url for url in urls}
    for future in as_completed(futures):
        url = futures[future]
        try:
            result = future.result()
            print(result)
        except Exception as e:
            print(f"{url} failed: {e}")

# Note: Python's GIL limits CPU-bound threading — use multiprocessing for CPU tasks
```

### Asyncio — async/await

```python
import asyncio
import aiohttp   # pip install aiohttp

# Coroutine — defined with async def
async def greet(name, delay):
    await asyncio.sleep(delay)   # non-blocking sleep
    print(f"Hello, {name}!")
    return name

# Run a coroutine
asyncio.run(greet("Alice", 1))

# Run multiple coroutines concurrently
async def main():
    # gather — run all concurrently, wait for all
    results = await asyncio.gather(
        greet("Alice", 1),
        greet("Bob", 0.5),
        greet("Carol", 0.1),
    )
    print(results)   # ['Alice', 'Bob', 'Carol']

asyncio.run(main())

# Task — schedule coroutine to run soon
async def main():
    task1 = asyncio.create_task(greet("Alice", 1))
    task2 = asyncio.create_task(greet("Bob", 0.5))
    
    await task1
    await task2

# Timeout
async def main():
    try:
        result = await asyncio.wait_for(greet("Alice", 10), timeout=3.0)
    except asyncio.TimeoutError:
        print("Timed out!")

# HTTP with aiohttp
async def fetch_url(session, url):
    async with session.get(url) as response:
        return await response.json()

async def fetch_all():
    urls = ['https://httpbin.org/get', 'https://httpbin.org/ip']
    async with aiohttp.ClientSession() as session:
        tasks = [fetch_url(session, url) for url in urls]
        results = await asyncio.gather(*tasks)
        return results

# Async generator
async def async_range(n):
    for i in range(n):
        await asyncio.sleep(0)   # yield control
        yield i

async def main():
    async for i in async_range(5):
        print(i)

# Async context manager
class AsyncDB:
    async def __aenter__(self):
        await asyncio.sleep(0.1)   # simulate connect
        return self
    
    async def __aexit__(self, *args):
        await asyncio.sleep(0.1)   # simulate disconnect

async def main():
    async with AsyncDB() as db:
        print("Using db")

# asyncio Queue for producer-consumer
async def producer(queue):
    for i in range(5):
        await queue.put(i)
        await asyncio.sleep(0.1)
    await queue.put(None)   # sentinel

async def consumer(queue):
    while True:
        item = await queue.get()
        if item is None:
            break
        print(f"Consumed: {item}")
        queue.task_done()

async def pipeline():
    queue = asyncio.Queue(maxsize=10)
    await asyncio.gather(producer(queue), consumer(queue))

asyncio.run(pipeline())
```

---

## 29. Multiprocessing

```python
from multiprocessing import Pool, Process, Queue, Manager, Value, Array
import os

# Basic process
def worker(n):
    print(f"PID {os.getpid()} computing {n}^2 = {n**2}")
    return n ** 2

# Pool — parallel map across processes
if __name__ == '__main__':   # REQUIRED on Windows/macOS
    
    with Pool(processes=4) as pool:
        results = pool.map(worker, range(8))
        print(results)
    
    # starmap — multiple arguments
    def add(a, b): return a + b
    with Pool() as pool:
        sums = pool.starmap(add, [(1,2),(3,4),(5,6)])
        print(sums)   # [3, 7, 11]
    
    # async variants
    with Pool() as pool:
        result = pool.map_async(worker, range(8))
        print(result.get())   # wait for completion

    # Shared memory
    counter = Value('i', 0)      # shared integer
    arr = Array('d', [1.0, 2.0, 3.0])   # shared double array
    
    # Manager — more flexible shared objects
    with Manager() as manager:
        shared_dict = manager.dict()
        shared_list = manager.list()
    
    # ProcessPoolExecutor (cleaner API)
    from concurrent.futures import ProcessPoolExecutor
    
    with ProcessPoolExecutor(max_workers=4) as executor:
        futures = [executor.submit(worker, n) for n in range(8)]
        for f in futures:
            print(f.result())
    
    # Chunked map for better performance
    with ProcessPoolExecutor() as executor:
        results = list(executor.map(worker, range(100), chunksize=10))
```

---

## 30. Networking & HTTP

```python
# ── urllib (built-in) ─────────────────────────────
import urllib.request, urllib.parse, json

url = 'https://api.github.com/users/octocat'
req = urllib.request.Request(url, headers={'User-Agent': 'Mozilla/5.0'})
with urllib.request.urlopen(req) as resp:
    data = json.loads(resp.read())
    print(data['name'])

# POST with urllib
post_data = urllib.parse.urlencode({'key': 'value'}).encode()
req = urllib.request.Request(url, data=post_data, method='POST')

# ── requests (pip install requests) ───────────────
import requests

# GET
r = requests.get('https://api.github.com/users/octocat')
r.raise_for_status()   # raise HTTPError for 4xx/5xx
print(r.status_code)   # 200
print(r.headers['Content-Type'])
user = r.json()        # parse JSON response

# GET with parameters
r = requests.get('https://httpbin.org/get',
                 params={'key': 'value', 'count': 5},
                 timeout=10)

# POST
r = requests.post('https://httpbin.org/post',
                  json={'name': 'Alice'},           # JSON body
                  headers={'Authorization': 'Bearer TOKEN'})

# File upload
with open('file.txt', 'rb') as f:
    r = requests.post('https://httpbin.org/post', files={'file': f})

# Session (reuse connection, share headers/cookies)
with requests.Session() as s:
    s.headers.update({'User-Agent': 'MyApp/1.0'})
    s.auth = ('username', 'password')
    r1 = s.get('https://example.com/api/data')
    r2 = s.get('https://example.com/api/more')

# Timeout & retries
from requests.adapters import HTTPAdapter
from urllib3.util.retry import Retry

retry = Retry(total=3, backoff_factor=0.5,
              status_forcelist=[429, 500, 502, 503, 504])
s = requests.Session()
s.mount('https://', HTTPAdapter(max_retries=retry))
r = s.get('https://example.com', timeout=(3.05, 27))
# timeout=(connect_timeout, read_timeout)

# ── socket (low-level) ────────────────────────────
import socket

# Simple TCP client
with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect(('example.com', 80))
    s.send(b'GET / HTTP/1.0\r\nHost: example.com\r\n\r\n')
    response = s.recv(4096)

# Simple TCP server
with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as server:
    server.bind(('', 8080))
    server.listen(5)
    conn, addr = server.accept()
    with conn:
        data = conn.recv(1024)
        conn.sendall(b'HTTP/1.0 200 OK\r\n\r\nHello!')
```

---

## 31. Working with JSON, CSV & XML

### JSON

```python
import json

# Python → JSON string
data = {'name': 'Alice', 'age': 30, 'scores': [90, 85, 92], 'active': True}
json_str = json.dumps(data)
json_pretty = json.dumps(data, indent=2, sort_keys=True)
print(json_pretty)

# JSON string → Python
loaded = json.loads(json_str)
print(loaded['name'])   # Alice

# File I/O
with open('data.json', 'w') as f:
    json.dump(data, f, indent=2)

with open('data.json') as f:
    loaded = json.load(f)

# Custom types
from datetime import datetime

class DateTimeEncoder(json.JSONEncoder):
    def default(self, obj):
        if isinstance(obj, datetime):
            return obj.isoformat()
        return super().default(obj)

json.dumps({'ts': datetime.now()}, cls=DateTimeEncoder)

# Decode with object_hook
def as_datetime(d):
    if 'ts' in d:
        d['ts'] = datetime.fromisoformat(d['ts'])
    return d

json.loads('{"ts":"2024-07-15T10:00:00"}', object_hook=as_datetime)
```

### CSV

```python
import csv

# Write
with open('people.csv', 'w', newline='', encoding='utf-8') as f:
    writer = csv.writer(f)
    writer.writerow(['name', 'age', 'city'])          # header
    writer.writerows([
        ['Alice', 30, 'NYC'],
        ['Bob', 25, 'LA'],
        ['Carol', 35, 'Chicago'],
    ])

# Read with DictReader (headers become keys)
with open('people.csv', encoding='utf-8') as f:
    reader = csv.DictReader(f)
    for row in reader:
        print(row['name'], row['age'])

# DictWriter
with open('output.csv', 'w', newline='') as f:
    fieldnames = ['name', 'age', 'city']
    writer = csv.DictWriter(f, fieldnames=fieldnames)
    writer.writeheader()
    writer.writerow({'name': 'Alice', 'age': 30, 'city': 'NYC'})

# Custom dialect
csv.register_dialect('pipes', delimiter='|', quotechar='"')
with open('data.csv') as f:
    reader = csv.reader(f, dialect='pipes')
```

### XML

```python
import xml.etree.ElementTree as ET

# Parse XML
tree = ET.parse('data.xml')
root = tree.getroot()

# Or from string
xml_str = '<root><item id="1">Hello</item><item id="2">World</item></root>'
root = ET.fromstring(xml_str)

# Navigate
for item in root.findall('item'):
    print(item.get('id'))    # attribute
    print(item.text)         # text content

# XPath-like queries
items = root.findall('.//item[@id="1"]')

# Create XML
root = ET.Element('catalog')
book = ET.SubElement(root, 'book', id='1')
title = ET.SubElement(book, 'title')
title.text = 'Python Basics'

tree = ET.ElementTree(root)
ET.indent(tree, space='  ')   # pretty-print (Python 3.9+)
tree.write('output.xml', xml_declaration=True, encoding='utf-8')
```

---

## 32. Databases — SQLite & SQLAlchemy

### SQLite (built-in)

```python
import sqlite3

# Connect (creates file if not exists; use ':memory:' for in-memory)
conn = sqlite3.connect('mydb.sqlite3')
conn.row_factory = sqlite3.Row   # rows as dict-like objects
cur = conn.cursor()

# Create table
cur.execute("""
    CREATE TABLE IF NOT EXISTS users (
        id    INTEGER PRIMARY KEY AUTOINCREMENT,
        name  TEXT NOT NULL,
        age   INTEGER,
        email TEXT UNIQUE
    )
""")

# Insert (use ? placeholders — NEVER string formatting! SQL injection!)
cur.execute('INSERT INTO users (name, age, email) VALUES (?,?,?)',
            ('Alice', 30, 'alice@example.com'))

cur.executemany('INSERT INTO users (name, age) VALUES (?,?)',
                [('Bob', 25), ('Carol', 35), ('Dave', 28)])
conn.commit()

# Query
rows = cur.execute('SELECT * FROM users WHERE age > ?', (24,)).fetchall()
for row in rows:
    print(row['name'], row['age'])    # dict-like access

one = cur.execute('SELECT * FROM users WHERE name=?', ('Alice',)).fetchone()

# Update & Delete
cur.execute('UPDATE users SET age=? WHERE name=?', (31, 'Alice'))
cur.execute('DELETE FROM users WHERE age<?', (20,))
conn.commit()

# Transaction
try:
    cur.execute('INSERT INTO users (name) VALUES (?)', ('Eve',))
    cur.execute('INSERT INTO users (name) VALUES (?)', ('Frank',))
    conn.commit()
except sqlite3.IntegrityError:
    conn.rollback()
finally:
    conn.close()

# Context manager (auto-commits or rolls back)
with sqlite3.connect('mydb.sqlite3') as conn:
    conn.execute('INSERT INTO users (name) VALUES (?)', ('Grace',))
    # auto-commits on exit, rolls back on exception
```

### SQLAlchemy ORM

```python
# pip install sqlalchemy
from sqlalchemy import create_engine, Column, Integer, String, ForeignKey, select
from sqlalchemy.orm import DeclarativeBase, Session, relationship

engine = create_engine('sqlite:///app.db', echo=False)

class Base(DeclarativeBase):
    pass

class User(Base):
    __tablename__ = 'users'
    
    id       = Column(Integer, primary_key=True)
    name     = Column(String(50), nullable=False)
    age      = Column(Integer)
    posts    = relationship('Post', back_populates='author')
    
    def __repr__(self):
        return f"<User {self.id}: {self.name}>"

class Post(Base):
    __tablename__ = 'posts'
    
    id        = Column(Integer, primary_key=True)
    title     = Column(String(200))
    user_id   = Column(Integer, ForeignKey('users.id'))
    author    = relationship('User', back_populates='posts')

Base.metadata.create_all(engine)

# CRUD
with Session(engine) as session:
    # Create
    alice = User(name='Alice', age=30)
    session.add(alice)
    session.add_all([User(name='Bob', age=25), User(name='Carol', age=35)])
    session.commit()
    
    # Read
    users = session.scalars(select(User).where(User.age > 24)).all()
    user = session.get(User, 1)  # by primary key
    
    # Update
    user.age = 31
    session.commit()
    
    # Delete
    session.delete(user)
    session.commit()
    
    # Joins
    stmt = (select(User, Post)
            .join(Post, User.id == Post.user_id)
            .where(User.name == 'Alice'))
    results = session.execute(stmt).all()
```

---

## 33. Testing — unittest & pytest

### unittest (built-in)

```python
import unittest

def add(a, b): return a + b
def divide(a, b):
    if b == 0: raise ZeroDivisionError("Cannot divide by zero")
    return a / b

class TestMathFunctions(unittest.TestCase):
    
    def setUp(self):        # runs before EACH test method
        self.nums = [1, 2, 3, 4, 5]
    
    def tearDown(self):     # runs after EACH test method
        pass
    
    @classmethod
    def setUpClass(cls):    # runs once before ALL tests
        cls.expensive_resource = "setup"
    
    @classmethod
    def tearDownClass(cls): # runs once after ALL tests
        pass
    
    def test_add_positive(self):
        self.assertEqual(add(2, 3), 5)
    
    def test_add_negative(self):
        self.assertEqual(add(-1, 1), 0)
    
    def test_add_floats(self):
        self.assertAlmostEqual(add(0.1, 0.2), 0.3, places=10)
    
    def test_divide_raises(self):
        with self.assertRaises(ZeroDivisionError):
            divide(10, 0)
    
    def test_divide_raises_message(self):
        with self.assertRaisesRegex(ZeroDivisionError, "Cannot"):
            divide(10, 0)
    
    def test_list_contents(self):
        self.assertIn(3, self.nums)
        self.assertNotIn(10, self.nums)
        self.assertEqual(len(self.nums), 5)
    
    @unittest.skip("Not implemented yet")
    def test_skip_me(self):
        pass
    
    @unittest.skipIf(True, "Skipping on this platform")
    def test_conditional_skip(self):
        pass

# Run: python -m unittest test_module.py -v
```

### pytest

```python
# pip install pytest
# Run: pytest tests/ -v

import pytest

# Simple test functions (no class needed)
def test_add_positive():
    assert add(2, 3) == 5

def test_add_negative():
    assert add(-1, 1) == 0

# Test exceptions
def test_divide_raises():
    with pytest.raises(ZeroDivisionError, match="Cannot"):
        divide(10, 0)

# Parametrize — run same test with different inputs
@pytest.mark.parametrize('a,b,expected', [
    (1, 2, 3),
    (0, 0, 0),
    (-1, -1, -2),
    (100, 200, 300),
])
def test_add_parametrized(a, b, expected):
    assert add(a, b) == expected

# Fixtures — reusable setup
@pytest.fixture
def sample_data():
    return {'users': ['Alice', 'Bob'], 'count': 2}

@pytest.fixture
def db_connection():
    conn = sqlite3.connect(':memory:')
    yield conn      # provide the fixture
    conn.close()    # teardown after test

def test_users(sample_data):
    assert len(sample_data['users']) == sample_data['count']

# Marks
@pytest.mark.slow
def test_slow():
    time.sleep(1)

@pytest.mark.skipif(sys.platform == 'win32', reason="Not on Windows")
def test_unix_only():
    pass

# Mocking
from unittest.mock import Mock, MagicMock, patch, call

def test_with_mock():
    mock_db = Mock()
    mock_db.find.return_value = {'id': 1, 'name': 'Alice'}
    
    result = mock_db.find(1)
    assert result['name'] == 'Alice'
    mock_db.find.assert_called_once_with(1)

def test_with_patch():
    with patch('requests.get') as mock_get:
        mock_get.return_value.status_code = 200
        mock_get.return_value.json.return_value = {'key': 'value'}
        
        response = requests.get('https://example.com')
        assert response.status_code == 200

@patch('mymodule.requests.get')
def test_with_decorator(mock_get):
    mock_get.return_value.json.return_value = {}
    ...

# conftest.py — shared fixtures across test files
# pytest.ini or pyproject.toml — configuration
```

---

## 34. Debugging & Profiling

```python
# ── pdb — Python Debugger ─────────────────────────
import pdb

def buggy_function(x):
    pdb.set_trace()    # breakpoint — drops into interactive debugger
    result = x * 2
    return result

# Python 3.7+ built-in breakpoint()
def buggy2(x):
    breakpoint()       # same as pdb.set_trace()
    return x * 2

# pdb commands:
# n(ext)     — execute current line, stop at next
# s(tep)     — step INTO function call
# c(ontinue) — continue until next breakpoint
# l(ist)     — show source code
# p <expr>   — print expression
# pp <expr>  — pretty-print
# w(here)    — show call stack
# u(p)/d(own) — move up/down call stack
# b(reak) [line] — set breakpoint
# r(eturn)   — run until return
# q(uit)     — quit debugger

# ── logging ───────────────────────────────────────
import logging

logging.basicConfig(
    level=logging.DEBUG,
    format='%(asctime)s - %(name)s - %(levelname)s - %(message)s',
    handlers=[
        logging.FileHandler('app.log'),
        logging.StreamHandler()
    ]
)

logger = logging.getLogger(__name__)
logger.debug("Detailed info for diagnosing problems")
logger.info("General info about program execution")
logger.warning("Something unexpected happened")
logger.error("Serious problem occurred")
logger.critical("Program may not be able to continue")
logger.exception("Exception occurred", exc_info=True)  # includes traceback

# ── cProfile ──────────────────────────────────────
import cProfile, pstats

def my_function():
    return sum(i**2 for i in range(100000))

# Run profiler
with cProfile.Profile() as pr:
    my_function()

stats = pstats.Stats(pr)
stats.sort_stats('cumulative')   # or 'time', 'calls'
stats.print_stats(10)            # top 10

# Or via command line:
# python -m cProfile -s cumulative myscript.py

# ── timeit ────────────────────────────────────────
import timeit

# Inline usage
t = timeit.timeit('[x**2 for x in range(100)]', number=10000)
print(f"{t:.4f}s")

# Timer object
timer = timeit.Timer(
    stmt='sum(squares)',
    setup='squares = [x**2 for x in range(100)]'
)
times = timer.repeat(repeat=5, number=1000)
print(f"Best: {min(times):.6f}s")

# ── memory_profiler ───────────────────────────────
# pip install memory_profiler
# from memory_profiler import profile
# @profile
# def my_func():
#     ...
# Run: python -m memory_profiler script.py

# ── tracemalloc — built-in memory tracing ─────────
import tracemalloc

tracemalloc.start()

# ... code to profile ...
data = [list(range(1000)) for _ in range(100)]

snapshot = tracemalloc.take_snapshot()
stats = snapshot.statistics('lineno')
for stat in stats[:5]:
    print(stat)
```

---

## 35. Virtual Environments & pip

```bash
# Create virtual environment
python -m venv myenv
python3.12 -m venv myenv   # specific version

# Activate
source myenv/bin/activate        # macOS/Linux
myenv\Scripts\activate            # Windows CMD
myenv\Scripts\Activate.ps1        # Windows PowerShell

# Deactivate
deactivate

# pip commands
pip install requests                          # install latest
pip install requests==2.31.0                  # specific version
pip install 'requests>=2.28,<3.0'             # version range
pip install requests[security]                # with extras
pip install -e .                              # editable install (dev)
pip install -r requirements.txt               # from file
pip freeze > requirements.txt                 # save dependencies
pip list                                      # list installed
pip show requests                             # info about package
pip uninstall requests                        # remove
pip install --upgrade requests                # upgrade
pip check                                     # check for conflicts
pip download requests -d ./packages           # download without installing
pip install --no-index --find-links=./packages requests  # install offline
```

### pyproject.toml (Modern Standard)

```toml
[build-system]
requires = ["setuptools>=61", "wheel"]
build-backend = "setuptools.backends.legacy:build"

[project]
name = "mypackage"
version = "0.1.0"
description = "A sample Python project"
readme = "README.md"
requires-python = ">=3.11"
license = {text = "MIT"}
authors = [{name = "Alice", email = "alice@example.com"}]

dependencies = [
    "requests>=2.28",
    "click>=8.0",
]

[project.optional-dependencies]
dev = ["pytest", "black", "ruff", "mypy"]
docs = ["sphinx", "sphinx-rtd-theme"]

[project.scripts]
my-tool = "mypackage.cli:main"

[tool.black]
line-length = 88

[tool.ruff]
select = ["E", "F", "I"]
```

```bash
# uv — ultra-fast package manager (recommended)
pip install uv
uv venv
uv pip install requests
uv pip sync requirements.txt
uv run python script.py

# pipx — install CLI tools in isolated environments
pip install pipx
pipx install black
pipx install httpie
```

---

## 36. Advanced Python Patterns

### Singleton Pattern

```python
class Singleton:
    _instance = None

    def __new__(cls, *args, **kwargs):
        if cls._instance is None:
            cls._instance = super().__new__(cls)
        return cls._instance

a = Singleton()
b = Singleton()
print(a is b)   # True

# Thread-safe Singleton
import threading

class ThreadSafeSingleton:
    _instance = None
    _lock = threading.Lock()

    def __new__(cls):
        with cls._lock:
            if cls._instance is None:
                cls._instance = super().__new__(cls)
        return cls._instance
```

### Observer Pattern

```python
class EventEmitter:
    def __init__(self):
        self._listeners: dict[str, list] = {}

    def on(self, event: str, callback):
        self._listeners.setdefault(event, []).append(callback)
        return self   # method chaining

    def off(self, event: str, callback):
        self._listeners.get(event, []).remove(callback)

    def emit(self, event: str, *args, **kwargs):
        for cb in self._listeners.get(event, []):
            cb(*args, **kwargs)

emitter = EventEmitter()
emitter.on("data", lambda x: print(f"Received: {x}"))
emitter.on("data", lambda x: print(f"Logged: {x}"))
emitter.emit("data", 42)
```

### Factory Pattern

```python
class Animal: pass
class Dog(Animal):
    def speak(self): return "Woof!"
class Cat(Animal):
    def speak(self): return "Meow!"
class Bird(Animal):
    def speak(self): return "Tweet!"

class AnimalFactory:
    _registry = {'dog': Dog, 'cat': Cat, 'bird': Bird}

    @classmethod
    def register(cls, name, animal_class):
        cls._registry[name] = animal_class

    @classmethod
    def create(cls, animal_type: str) -> Animal:
        cls_ = cls._registry.get(animal_type)
        if cls_ is None:
            raise ValueError(f"Unknown animal: {animal_type}")
        return cls_()

dog = AnimalFactory.create('dog')
print(dog.speak())   # Woof!
```

### Abstract Base Classes

```python
from abc import ABC, abstractmethod

class Shape(ABC):
    @abstractmethod
    def area(self) -> float: ...

    @abstractmethod
    def perimeter(self) -> float: ...

    def describe(self) -> str:
        return f"Area={self.area():.2f}, Perimeter={self.perimeter():.2f}"

class Circle(Shape):
    def __init__(self, r): self.r = r
    def area(self):        return 3.14159 * self.r ** 2
    def perimeter(self):   return 2 * 3.14159 * self.r

class Rectangle(Shape):
    def __init__(self, w, h): self.w, self.h = w, h
    def area(self):        return self.w * self.h
    def perimeter(self):   return 2 * (self.w + self.h)

# Shape()  # TypeError: Can't instantiate abstract class Shape
c = Circle(5)
print(c.describe())   # Area=78.54, Perimeter=31.42
```

---

## 37. Memory Management & Garbage Collection

```python
import gc, sys, weakref

# Reference counting — Python's primary memory management
a = [1, 2, 3]
print(sys.getrefcount(a))   # 2 (a + getrefcount's temp reference)

b = a            # refcount → 3
c = a            # refcount → 4
del b            # refcount → 3
del c            # refcount → 2
del a            # refcount → 0 → object freed immediately!

# Object sizes
print(sys.getsizeof(42))             # 28 bytes
print(sys.getsizeof([]))             # 56 bytes (empty list overhead)
print(sys.getsizeof(list(range(1000))))   # ~8056 bytes

# Garbage collector handles reference cycles
class Node:
    def __init__(self):
        self.next = None

a = Node()
b = Node()
a.next = b
b.next = a   # cycle!
del a, b     # refcount > 0, so gc is needed

gc.collect()   # force garbage collection
gc.get_count() # (gen0, gen1, gen2) collection counts
gc.get_threshold()  # thresholds for each generation

# Weak references — reference without preventing garbage collection
class ExpensiveObject:
    def __init__(self, data):
        self.data = data
    def __del__(self):
        print("Cleaned up!")

obj = ExpensiveObject("big data")
weak = weakref.ref(obj)         # weak reference

print(weak())                   # <ExpensiveObject ...>  (still alive)
del obj                         # Cleaned up!
print(weak())                   # None  (garbage collected!)

# WeakValueDictionary — cache that doesn't prevent GC
cache = weakref.WeakValueDictionary()
obj = ExpensiveObject("data")
cache['key'] = obj
del obj  # automatically removed from cache!

# __slots__ — eliminate __dict__ to save memory
class RegularPoint:
    def __init__(self, x, y):
        self.x, self.y = x, y
    # has __dict__ — can add arbitrary attributes

class SlottedPoint:
    __slots__ = ['x', 'y']   # no __dict__ created
    def __init__(self, x, y):
        self.x, self.y = x, y
    # cannot add arbitrary attributes

# Savings with __slots__:
regular = RegularPoint(1, 2)
slotted = SlottedPoint(1, 2)
print(sys.getsizeof(regular))   # ~48 bytes + __dict__ (~232 bytes)
print(sys.getsizeof(slotted))   # ~48 bytes (no __dict__!)
# ~50% memory reduction for millions of instances
```

---

## 38. Metaclasses & Descriptors

### Metaclasses

A metaclass is a "class of a class" — it controls how classes themselves are created.

```python
# type is the default metaclass of all classes
print(type(int))     # <class 'type'>
print(type(str))     # <class 'type'>
print(type(list))    # <class 'type'>

# Creating a class dynamically with type
MyClass = type('MyClass', (object,), {
    'x': 10,
    'greet': lambda self: f"Hello from {type(self).__name__}"
})

# Custom metaclass
class SingletonMeta(type):
    _instances = {}

    def __call__(cls, *args, **kwargs):
        if cls not in cls._instances:
            cls._instances[cls] = super().__call__(*args, **kwargs)
        return cls._instances[cls]

class Database(metaclass=SingletonMeta):
    def __init__(self):
        self.connection = 'connected'

d1 = Database()
d2 = Database()
print(d1 is d2)   # True

# Metaclass that validates class definition
class ValidateMeta(type):
    def __new__(mcs, name, bases, namespace):
        # Ensure all methods have docstrings
        for key, value in namespace.items():
            if callable(value) and not key.startswith('_'):
                if not value.__doc__:
                    raise TypeError(f"Method '{key}' must have a docstring")
        return super().__new__(mcs, name, bases, namespace)

# Abstract-like registry
class PluginMeta(type):
    plugins = {}
    def __init__(cls, name, bases, namespace):
        super().__init__(name, bases, namespace)
        if bases:  # skip base class itself
            PluginMeta.plugins[name] = cls

class Plugin(metaclass=PluginMeta): pass
class MyPlugin(Plugin): pass
class AnotherPlugin(Plugin): pass
print(PluginMeta.plugins)   # {'MyPlugin': ..., 'AnotherPlugin': ...}
```

### Descriptors

The descriptor protocol defines how attribute access works (`__get__`, `__set__`, `__delete__`).

```python
# Data descriptor (defines __set__ or __delete__)
class TypedAttribute:
    def __init__(self, name, expected_type):
        self.name = name
        self.expected_type = expected_type

    def __set_name__(self, owner, name):   # called when class is defined (Python 3.6+)
        self.name = name

    def __set__(self, instance, value):
        if not isinstance(value, self.expected_type):
            raise TypeError(
                f"{self.name} must be {self.expected_type.__name__}, "
                f"got {type(value).__name__}"
            )
        instance.__dict__[self.name] = value

    def __get__(self, instance, owner):
        if instance is None:
            return self   # accessed on the class itself
        return instance.__dict__.get(self.name)

    def __delete__(self, instance):
        del instance.__dict__[self.name]

class Person:
    name = TypedAttribute('name', str)
    age  = TypedAttribute('age', int)

    def __init__(self, name, age):
        self.name = name
        self.age  = age

p = Person("Alice", 30)
p.age = "thirty"   # TypeError: age must be int

# Non-data descriptor (only __get__)
class CachedProperty:
    def __init__(self, func):
        self.func = func
        self.attrname = None

    def __set_name__(self, owner, name):
        self.attrname = f'_cached_{name}'

    def __get__(self, instance, owner):
        if instance is None:
            return self
        if not hasattr(instance, self.attrname):
            setattr(instance, self.attrname, self.func(instance))
        return getattr(instance, self.attrname)

class Circle:
    def __init__(self, radius):
        self.radius = radius

    @CachedProperty
    def area(self):
        print("Computing area...")
        return 3.14159 * self.radius ** 2

c = Circle(5)
print(c.area)   # Computing area...  78.539...
print(c.area)   # 78.539...  (cached, no recomputation)
```

---

## 39. C Extensions & ctypes

```python
import ctypes

# Load shared library
# libc = ctypes.CDLL('libc.so.6')      # Linux
# libc = ctypes.CDLL('libc.dylib')     # macOS
# libc = ctypes.cdll.msvcrt            # Windows

libc = ctypes.CDLL(None)   # current process

# Define argument and return types (IMPORTANT for correctness)
libc.strlen.argtypes = [ctypes.c_char_p]
libc.strlen.restype  = ctypes.c_size_t
print(libc.strlen(b"hello"))   # 5

# C data types mapping
# ctypes.c_int, c_long, c_double, c_float, c_char, c_char_p
# ctypes.c_bool, c_void_p, c_size_t, c_ssize_t

# Create C structs
class Point(ctypes.Structure):
    _fields_ = [
        ('x', ctypes.c_double),
        ('y', ctypes.c_double),
    ]

p = Point(1.5, 2.5)
print(p.x, p.y)   # 1.5 2.5

# Arrays
IntArray5 = ctypes.c_int * 5
arr = IntArray5(1, 2, 3, 4, 5)
print(list(arr))   # [1, 2, 3, 4, 5]

# Pointers
x = ctypes.c_int(42)
ptr = ctypes.pointer(x)
print(ptr.contents.value)   # 42
ptr.contents.value = 100
print(x.value)              # 100

# Calling a function from a compiled .so/.dll
# Suppose you have: int add(int a, int b) { return a + b; }
# Compiled as: gcc -shared -o libmath.so math.c
mylib = ctypes.CDLL('./libmath.so')
mylib.add.argtypes = [ctypes.c_int, ctypes.c_int]
mylib.add.restype  = ctypes.c_int
print(mylib.add(3, 4))   # 7

# cffi — more Pythonic C FFI (pip install cffi)
from cffi import FFI
ffi = FFI()
ffi.cdef("int strlen(const char *s);")
C = ffi.dlopen(None)
print(C.strlen(b"hello"))   # 5

# For CPU-intensive work, alternatives to C extensions:
# Cython      — compile Python-like code to C (pip install cython)
# pybind11    — wrap C++ for Python
# ctypes      — call C from Python (no compilation needed)
# cffi        — C Foreign Function Interface
# numba       — JIT compiler for numerical Python (pip install numba)
# numpy       — C-backed array operations (pip install numpy)
```

---

## 40. Best Practices & Style Guide

### PEP 8 — The Python Style Guide

```python
# ── Naming Conventions ────────────────────────────
snake_case_variable = 42           # variables & functions
UPPER_CASE_CONSTANT = 3.14         # constants
CapWordsClass = True               # classes
_single_leading = "protected"      # protected (convention)
__double_leading = "private"       # private (name-mangled)
__dunder__ = "magic"               # magic/dunder methods

# ── Indentation & Line Length ─────────────────────
def function():
    if True:
        pass   # 4 spaces, never tabs

# Max 79 chars per line (99 is also common in modern codebases)
# Use \ or parentheses for line continuation
result = (very_long_variable_name
          + another_long_variable
          + yet_another_one)

# ── Imports ───────────────────────────────────────
# 1. Standard library
import os
import sys
from pathlib import Path

# 2. Third-party
import requests
import numpy as np

# 3. Local
from mypackage import utils

# ── Whitespace ────────────────────────────────────
# Good
x = 5
y = [1, 2, 3]
result = func(arg1, arg2)
d = {'key': 'value'}

# Bad
x=5
y=[ 1,2,3 ]
result = func( arg1,arg2 )
```

### Idiomatic Python (Pythonic Code)

```python
# ❌ Non-Pythonic — C-style loop
i = 0
while i < len(items):
    print(items[i])
    i += 1

# ✅ Pythonic — for-in
for item in items:
    print(item)

# ❌ Non-Pythonic — manual index
for i in range(len(items)):
    print(i, items[i])

# ✅ Pythonic — enumerate
for i, item in enumerate(items):
    print(i, item)

# ❌ Non-Pythonic — manual parallel iteration
for i in range(len(names)):
    print(names[i], scores[i])

# ✅ Pythonic — zip
for name, score in zip(names, scores):
    print(name, score)

# ❌ Non-Pythonic — check truthiness
if x == True: ...
if len(lst) == 0: ...
if s == "": ...

# ✅ Pythonic
if x: ...
if not lst: ...
if not s: ...

# ❌ Non-Pythonic — string concatenation
result = ""
for word in words:
    result += word + " "

# ✅ Pythonic
result = " ".join(words)

# ❌ Non-Pythonic — explicit key check before set
if 'key' not in d:
    d['key'] = default
val = d['key']

# ✅ Pythonic
val = d.setdefault('key', default)
# or:
val = d.get('key', default)

# ❌ Non-Pythonic — manual swap
temp = a
a = b
b = temp

# ✅ Pythonic
a, b = b, a

# ✅ Use any() / all()
any(x > 0 for x in nums)    # True if at least one positive
all(x > 0 for x in nums)    # True if all positive

# ✅ Use walrus operator for assign-and-test
import re
if m := re.search(r'\d+', text):
    print(m.group())

# ✅ EAFP (Easier to Ask Forgiveness than Permission) — Pythonic
try:
    value = my_dict['key']
except KeyError:
    value = default

# vs LBYL (Look Before You Leap) — less Pythonic
if 'key' in my_dict:
    value = my_dict['key']

# ✅ Context managers for resource management
with open('file.txt') as f:      # auto-close
    data = f.read()

with threading.Lock() as lock:   # auto-release
    shared_data += 1
```

### Code Quality Tools

```bash
# Install all essential tools
pip install black ruff mypy pytest pre-commit

# black — opinionated code formatter
black my_script.py             # format
black --check my_script.py    # check without modifying
black --diff my_script.py     # show diff

# ruff — extremely fast linter (replaces flake8, isort, pylint)
ruff check my_script.py       # lint
ruff check --fix my_script.py # auto-fix where possible
ruff format my_script.py      # format (black-compatible)

# mypy — static type checker
mypy my_script.py
mypy --strict my_script.py    # stricter checks
mypy --ignore-missing-imports my_script.py

# pytest
pytest                         # run all tests
pytest -v                      # verbose
pytest tests/test_math.py      # specific file
pytest -k "test_add"           # filter by name
pytest -x                      # stop on first failure
pytest --cov=mypackage         # with coverage

# pre-commit — run checks before every commit
# .pre-commit-config.yaml:
# repos:
#   - repo: https://github.com/psf/black
#     hooks: [{id: black}]
#   - repo: https://github.com/charliermarsh/ruff-pre-commit
#     hooks: [{id: ruff}]
pre-commit install
pre-commit run --all-files
```

### Docstrings

```python
def calculate_distance(x1: float, y1: float, x2: float, y2: float) -> float:
    """Calculate the Euclidean distance between two points.

    Args:
        x1: x-coordinate of the first point.
        y1: y-coordinate of the first point.
        x2: x-coordinate of the second point.
        y2: y-coordinate of the second point.

    Returns:
        The Euclidean distance as a float.

    Raises:
        TypeError: If any argument is not a number.

    Example:
        >>> calculate_distance(0, 0, 3, 4)
        5.0
        >>> calculate_distance(1, 1, 4, 5)
        5.0
    """
    return ((x2 - x1)**2 + (y2 - y1)**2)**0.5
```

### The Zen of Python

```python
import this
```

```
Beautiful is better than ugly.
Explicit is better than implicit.
Simple is better than complex.
Complex is better than complicated.
Flat is better than nested.
Sparse is better than dense.
Readability counts.
Special cases aren't special enough to break the rules.
Although practicality beats purity.
Errors should never pass silently.
Unless explicitly silenced.
In the face of ambiguity, refuse the temptation to guess.
There should be one— and preferably only one —obvious way to do it.
Although that way may not be obvious at first unless you're Dutch.
Now is better than never.
Although never is often better than *right* now.
If the implementation is hard to explain, it's a bad idea.
If the implementation is easy to explain, it may be a good idea.
Namespaces are one honking great idea — let's do more of those!
```

---

## Quick Reference Card

| Concept | Syntax | Notes |
|---|---|---|
| List comp | `[x for x in lst if cond]` | Most common |
| Dict comp | `{k:v for k,v in d.items()}` | — |
| Set comp | `{x for x in lst}` | Unique values |
| Generator | `(x for x in lst)` | Lazy |
| Lambda | `lambda x: x+1` | Anonymous fn |
| Ternary | `a if cond else b` | Inline if |
| Walrus | `if x := expr:` | Assign+test |
| Unpack | `a, *b, c = lst` | Star unpack |
| f-string | `f"{val:.2f}"` | Python 3.6+ |
| Type hint | `def f(x: int) -> str:` | Use mypy |
| Dataclass | `@dataclass` | Auto `__init__` |
| Property | `@property` | Getter/setter |
| Abstract | `@abstractmethod` | Force override |
| Context mgr | `with x as y:` | Resource mgmt |
| Decorator | `@my_decorator` | Wrap function |
| Async | `async def` + `await` | Non-blocking |

---

*Python Complete Reference Guide — Beginner to Super Advanced*
*Keep coding. Keep learning. Stay Pythonic. 🐍*
