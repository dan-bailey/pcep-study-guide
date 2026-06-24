# PCEP Certification Study Guide
## Python Certified Entry-Level Programmer (Exam PCEP-30-02)

---

## Exam Overview

**Total Sections:** 4  
**Total Items:** 30  
**Time Limit:** 45 minutes  
**Passing Score:** 70% (700/1000 points)

### Score Distribution:
- Section 1: Computer Programming and Python Fundamentals (18%) — 7 items
- Section 2: Control Flow — Conditional Blocks and Loops (29%) — 8 items
- Section 3: Data Collections — Tuples, Dictionaries, Lists, and Strings (25%) — 7 items
- Section 4: Functions and Exceptions (28%) — 8 items

---

## Section 1: Computer Programming and Python Fundamentals (18%)

### 1.1 Fundamental Terms and Definitions

#### Interpreting vs. Compilation

**Compiled languages** (e.g., C, C++)
- Source code → Compiler → Machine code
- Fast execution; must compile before running
- Errors caught at compile time

**Interpreted languages** (e.g., Python)
- Source code → Interpreter → Executes line by line
- Slower than compiled, but easier to run and debug
- Errors raised at runtime (when that line is reached)

Python is interpreted. The **interpreter** reads your `.py` file and executes it directly.

```python
# Python runs this line by line
print("Line 1")  # Executes immediately
print("Line 2")  # Then this
```

#### Lexis, Syntax, and Semantics

**Lexis (Lexical rules):** The valid "words" (tokens) of the language — keywords, identifiers, operators, literals.  
**Syntax:** The grammar rules — how tokens must be arranged.  
**Semantics:** The meaning of valid statements — what the code actually does.

```python
# Syntax error (invalid grammar):
if x = 5:   # Should be ==, not =

# Semantic error (valid syntax, wrong meaning):
average = total + count  # Should be / not +
```

---

### 1.2 Python's Logic and Structure

#### Keywords

Reserved words that have special meaning in Python. Cannot be used as variable names.

```
False    await    else     import   pass
None     break    except   in       raise
True     class    finally  is       return
and      continue for      lambda   try
as       def      from     nonlocal while
assert   del      global   not      with
async    elif     if       or       yield
```

```python
# Cannot do this:
for = 5        # SyntaxError! 'for' is a keyword
None = "test"  # SyntaxError! 'None' is a keyword
```

#### Instructions and Statements

A **statement** is a single executable unit of code. Each statement typically goes on its own line:

```python
x = 10          # Assignment statement
print(x)        # Expression statement
if x > 5:       # Compound statement
    print("big")
```

#### Indentation

Python uses **indentation** (spaces or tabs) to define code blocks. Unlike other languages that use `{}`, Python's structure is defined by whitespace.

```python
if True:
    print("Indented block")      # 4 spaces
    if True:
        print("Nested block")    # 8 spaces
print("Back to top level")      # No indent
```

**Rules:**
- Consistent indentation required within a block
- Convention: 4 spaces per level (PEP-8)
- Mixing tabs and spaces causes errors

#### Comments

```python
# This is a single-line comment

"""
This is a multi-line string,
often used as a docstring/comment block.
"""

def my_function():
    """This is a docstring — documents the function."""
    pass
```

---

### 1.3 Literals, Variables, and Numeral Systems

#### Data Types and Literals

**Boolean:**
```python
True
False
bool(0)     # False
bool(1)     # True
bool("")    # False (empty string)
bool("hi")  # True (non-empty)
```

**Integers:**
```python
x = 42
y = -7
z = 0
big = 1_000_000   # Underscores allowed for readability
```

**Floating-Point Numbers:**
```python
pi = 3.14159
small = 0.001
negative = -2.5
```

**Scientific Notation:**
```python
a = 3e2    # 300.0   (3 × 10²)
b = 1.5e3  # 1500.0
c = 2.5e-4 # 0.00025 (2.5 × 10⁻⁴)

print(type(3e2))  # <class 'float'>
```

**Strings:**
```python
single = 'Hello'
double = "World"
triple = """Multi
line"""
```

#### Numeral Systems

```python
# Decimal (base 10) — default
decimal = 255

# Binary (base 2) — prefix 0b
binary = 0b11111111   # = 255

# Octal (base 8) — prefix 0o
octal = 0o377         # = 255

# Hexadecimal (base 16) — prefix 0x
hexadecimal = 0xFF    # = 255

# Convert between bases
bin(255)    # '0b11111111'
oct(255)    # '0o377'
hex(255)    # '0xff'
int('ff', 16)   # 255 — parse hex string
int('377', 8)   # 255 — parse octal string
int('11111111', 2)  # 255 — parse binary string
```

#### Variables and Naming Conventions

```python
# Valid names
name = "Alice"
age = 30
_private = "hidden"
MY_CONSTANT = 100
camelCase = "ok but not Pythonic"
snake_case = "preferred"

# Invalid names
2fast = "error"      # Can't start with digit
my-var = "error"     # Hyphens not allowed
class = "error"      # Reserved keyword
```

**PEP-8 Naming Conventions:**
- `snake_case` for variables and functions
- `PascalCase` for classes
- `ALL_CAPS` for constants
- Avoid single-letter names except for loop counters (`i`, `j`, `k`)

---

### 1.4 Operators and Data Types

#### Numeric Operators

```python
# Basic arithmetic
10 + 3    # 13  — addition
10 - 3    # 7   — subtraction
10 * 3    # 30  — multiplication
10 / 3    # 3.333... — true division (always float)
10 // 3   # 3   — floor division (integer result)
10 % 3    # 1   — modulo (remainder)
10 ** 3   # 1000 — exponentiation

# Common gotcha
-10 // 3  # -4 (rounds toward negative infinity!)
10 // -3  # -4 (same reason)
```

#### String Operators

```python
# Concatenation
"Hello" + " " + "World"  # "Hello World"

# Repetition
"ha" * 3                 # "hahaha"
3 * "ha"                 # "hahaha"
```

#### Assignment and Shortcut Operators

```python
x = 10         # Basic assignment

x += 5         # x = x + 5  → 15
x -= 3         # x = x - 3  → 12
x *= 2         # x = x * 2  → 24
x /= 4         # x = x / 4  → 6.0
x //= 2        # x = x // 2 → 3.0
x **= 3        # x = x ** 3 → 27.0
x %= 5         # x = x % 5  → 2.0
```

#### Unary vs. Binary Operators

```python
# Binary — two operands
5 + 3   # + used as binary operator

# Unary — one operand
-5      # - used as unary operator (negation)
+5      # + used as unary (no effect)
not True  # not is a unary boolean operator
```

#### Operator Priorities (Highest to Lowest)

```
1. ** (exponentiation)
2. +x, -x, ~x (unary)
3. *, /, //, %
4. +, - (binary)
5. <<, >>
6. &
7. ^
8. |
9. ==, !=, >, >=, <, <=, is, is not, in, not in
10. not
11. and
12. or
```

```python
# Examples
2 + 3 * 4      # 14 (not 20 — * has higher priority)
2 ** 3 ** 2    # 512 (right-to-left: 3**2=9, 2**9=512)
(2 + 3) * 4   # 20 (parentheses override precedence)
```

#### Bitwise Operators

```python
a = 0b1100   # 12
b = 0b1010   # 10

~a           # -13 (bitwise NOT — flips all bits)
a & b        # 0b1000 = 8 (AND — both bits must be 1)
a | b        # 0b1110 = 14 (OR — either bit is 1)
a ^ b        # 0b0110 = 6 (XOR — exactly one bit is 1)
a << 2       # 0b110000 = 48 (shift left by 2)
a >> 1       # 0b0110 = 6 (shift right by 1)
```

#### Boolean Operators and Expressions

```python
True and True    # True
True and False   # False
False and True   # False

True or False    # True
False or False   # False

not True         # False
not False        # True

# Short-circuit evaluation
False and (1/0)  # False — right side never evaluated!
True or (1/0)    # True — right side never evaluated!
```

#### Relational Operators

```python
5 == 5    # True
5 != 3    # True
5 > 3     # True
5 >= 5    # True
3 < 5     # True
3 <= 5    # True

# Chaining comparisons
1 < 5 < 10     # True (Pythonic!)
1 < 5 > 3      # True
```

#### Floating-Point Accuracy

```python
# Floating-point numbers are not always exact
0.1 + 0.2        # 0.30000000000000004 (NOT 0.3)
0.1 + 0.2 == 0.3 # False!

# Safe comparison
abs(0.1 + 0.2 - 0.3) < 1e-9  # True — compare with tolerance
```

#### Type Casting

```python
int(3.9)       # 3    — truncates (not rounds)
int("42")      # 42   — string to int
int(True)      # 1
int(False)     # 0

float(5)       # 5.0
float("3.14")  # 3.14

str(42)        # "42"
str(3.14)      # "3.14"

bool(0)        # False
bool(0.0)      # False
bool("")       # False
bool(None)     # False
bool([])       # False — empty collections are falsy
bool([0])      # True  — non-empty is truthy
```

---

### 1.5 Input/Output Console Operations

#### print() Function

```python
# Basic output
print("Hello, World!")
print(42)
print(3.14)

# Multiple values
print("Name:", "Alice", "Age:", 30)
# Output: Name: Alice Age: 30

# sep parameter (default is space)
print("a", "b", "c", sep="-")     # a-b-c
print("a", "b", "c", sep="")      # abc
print("a", "b", "c", sep=", ")    # a, b, c

# end parameter (default is newline \n)
print("Hello", end=" ")
print("World")                     # Hello World (on one line)
print("Hello", end="!\n")          # Hello!
```

#### input() Function

```python
# input() always returns a STRING
name = input("Enter your name: ")
print("Hello,", name)

# Must convert to use as number
age_str = input("Enter your age: ")
age = int(age_str)            # Convert to integer

# Common one-liner
age = int(input("Enter age: "))
price = float(input("Enter price: "))
```

#### int() and float() for Input

```python
# With input
x = int(input("Enter integer: "))    # "42" → 42
y = float(input("Enter decimal: "))  # "3.14" → 3.14

# Error if invalid input:
int("hello")   # ValueError!
float("abc")   # ValueError!

# Always a good idea to wrap in try-except in real code
try:
    age = int(input("Enter age: "))
except ValueError:
    print("That's not a valid number!")
```

---

## Section 2: Control Flow — Conditional Blocks and Loops (29%)

### 2.1 Conditional Statements

#### if / if-else / if-elif / if-elif-else

```python
# Simple if
x = 10
if x > 5:
    print("Greater than 5")

# if-else
if x % 2 == 0:
    print("Even")
else:
    print("Odd")

# if-elif-else
score = 75
if score >= 90:
    grade = "A"
elif score >= 80:
    grade = "B"
elif score >= 70:
    grade = "C"
elif score >= 60:
    grade = "D"
else:
    grade = "F"
print(f"Grade: {grade}")   # Grade: C
```

#### Nesting Conditional Statements

```python
x = 15
if x > 0:
    if x > 10:
        print("Greater than 10")
    else:
        print("Between 0 and 10")
else:
    print("Zero or negative")
```

#### Ternary / Conditional Expression

```python
# value_if_true if condition else value_if_false
age = 20
status = "adult" if age >= 18 else "minor"
print(status)   # adult
```

---

### 2.2 Loops

#### while Loop

```python
# Basic while
count = 0
while count < 5:
    print(count)
    count += 1
# Prints: 0 1 2 3 4

# While with input validation
while True:
    user_input = input("Enter 'quit' to exit: ")
    if user_input == "quit":
        break
    print("You entered:", user_input)
```

#### for Loop

```python
# Iterate over a sequence
for char in "Python":
    print(char)   # P y t h o n (each on a line)

# Iterate over a list
fruits = ["apple", "banana", "cherry"]
for fruit in fruits:
    print(fruit)

# Iterate over range
for i in range(5):
    print(i)      # 0 1 2 3 4

for i in range(2, 8):
    print(i)      # 2 3 4 5 6 7

for i in range(0, 10, 2):
    print(i)      # 0 2 4 6 8

for i in range(10, 0, -1):
    print(i)      # 10 9 8 7 6 5 4 3 2 1
```

#### range() Function

```python
range(stop)           # 0 to stop-1
range(start, stop)    # start to stop-1
range(start, stop, step)  # with custom step

list(range(5))        # [0, 1, 2, 3, 4]
list(range(2, 7))     # [2, 3, 4, 5, 6]
list(range(0, 10, 3)) # [0, 3, 6, 9]
list(range(5, 0, -1)) # [5, 4, 3, 2, 1]
```

#### pass Instruction

```python
# Placeholder — does nothing, prevents syntax error
for i in range(5):
    pass   # Loop runs but does nothing

if True:
    pass   # Valid but empty block
```

#### break and continue

```python
# break — exit loop entirely
for i in range(10):
    if i == 5:
        break
    print(i)
# Prints: 0 1 2 3 4

# continue — skip rest of this iteration
for i in range(10):
    if i % 2 == 0:
        continue
    print(i)
# Prints: 1 3 5 7 9
```

#### while-else and for-else

The `else` clause runs when the loop completes **without hitting a `break`:**

```python
# for-else
for i in range(5):
    if i == 10:    # Never true
        break
    print(i)
else:
    print("Loop completed without break")   # This prints

# Practical use — searching
needle = 7
haystack = [1, 3, 5, 9]

for item in haystack:
    if item == needle:
        print("Found!")
        break
else:
    print("Not found")  # Prints because break never hit
```

#### Iterating Through Sequences

```python
# Using enumerate() for index + value
fruits = ["apple", "banana", "cherry"]
for i, fruit in enumerate(fruits):
    print(f"{i}: {fruit}")
# 0: apple
# 1: banana
# 2: cherry

# enumerate with custom start
for i, fruit in enumerate(fruits, start=1):
    print(f"{i}. {fruit}")
# 1. apple
# 2. banana
# 3. cherry
```

#### Nesting Loops

```python
# Multiplication table
for i in range(1, 4):
    for j in range(1, 4):
        print(f"{i}*{j}={i*j}", end="  ")
    print()
# 1*1=1  1*2=2  1*3=3
# 2*1=2  2*2=4  2*3=6
# 3*1=3  3*2=6  3*3=9

# break only exits INNER loop
for i in range(3):
    for j in range(3):
        if j == 1:
            break
        print(f"i={i}, j={j}")
# i=0, j=0
# i=1, j=0
# i=2, j=0
```

---

## Section 3: Data Collections (25%)

### 3.1 Lists

#### Creating Lists

```python
# Empty list
empty = []
empty = list()

# List with values
numbers = [1, 2, 3, 4, 5]
mixed = [1, "hello", 3.14, True]    # Can mix types
nested = [[1, 2], [3, 4], [5, 6]]   # List of lists
```

#### Indexing and Slicing

```python
fruits = ["apple", "banana", "cherry", "date", "elderberry"]

# Positive indexing (0-based)
fruits[0]    # "apple"
fruits[2]    # "cherry"

# Negative indexing (from end)
fruits[-1]   # "elderberry"
fruits[-2]   # "date"

# Slicing [start:stop:step]
fruits[1:3]    # ["banana", "cherry"]
fruits[:3]     # ["apple", "banana", "cherry"]
fruits[2:]     # ["cherry", "date", "elderberry"]
fruits[::2]    # ["apple", "cherry", "elderberry"]
fruits[::-1]   # Reversed list

# Modify by index (lists are mutable)
fruits[0] = "avocado"
```

#### len() Function

```python
numbers = [1, 2, 3, 4, 5]
len(numbers)    # 5
len([])         # 0
len("hello")    # 5 — works on strings too
```

#### List Methods

```python
fruits = ["banana", "apple"]

# Add elements
fruits.append("cherry")         # Add to end → ["banana", "apple", "cherry"]
fruits.insert(0, "avocado")     # Insert at index → ["avocado", "banana", ...]
fruits.extend(["date", "fig"])  # Add multiple items

# Remove elements
fruits.remove("banana")         # Remove by value (first occurrence)
popped = fruits.pop()           # Remove and return last item
popped = fruits.pop(1)         # Remove and return item at index 1
del fruits[0]                   # Delete by index

# Search
fruits.index("apple")           # Return index of first occurrence
fruits.count("apple")           # Count occurrences

# Sorting
fruits.sort()                   # Sort in place (modifies list)
fruits.sort(reverse=True)       # Sort descending

# Other
fruits.reverse()                # Reverse in place
copy = fruits.copy()            # Shallow copy
fruits.clear()                  # Remove all items
```

#### sorted() Function vs .sort() Method

```python
numbers = [3, 1, 4, 1, 5, 9, 2, 6]

# sorted() — returns NEW list, original unchanged
sorted_nums = sorted(numbers)         # [1, 1, 2, 3, 4, 5, 6, 9]
rev_sorted = sorted(numbers, reverse=True)  # [9, 6, 5, 4, 3, 1, 1, 2]
print(numbers)                        # [3, 1, 4, 1, 5, 9, 2, 6] — unchanged!

# .sort() — modifies list IN PLACE, returns None
numbers.sort()
print(numbers)    # [1, 1, 2, 3, 4, 5, 6, 9]
result = numbers.sort()
print(result)     # None — common mistake!
```

#### del Instruction

```python
numbers = [1, 2, 3, 4, 5]

del numbers[2]      # Remove index 2 → [1, 2, 4, 5]
del numbers[1:3]    # Remove slice → [1, 5]
del numbers         # Delete the variable entirely
```

#### in and not in Operators

```python
fruits = ["apple", "banana", "cherry"]

"apple" in fruits      # True
"mango" in fruits      # False
"mango" not in fruits  # True

# Also works on strings
"py" in "python"       # True
```

#### List Comprehensions

```python
# [expression for item in iterable if condition]
squares = [x**2 for x in range(6)]             # [0, 1, 4, 9, 16, 25]
evens = [x for x in range(10) if x % 2 == 0]  # [0, 2, 4, 6, 8]
upper = [c.upper() for c in "hello"]           # ['H', 'E', 'L', 'L', 'O']
```

#### Copying and Cloning

```python
original = [1, 2, 3]

# Alias — NOT a copy! Both point to same list
alias = original
alias.append(4)
print(original)   # [1, 2, 3, 4] — original changed!

# Proper shallow copy
copy1 = original.copy()
copy2 = original[:]       # Slice copy
copy3 = list(original)    # list() constructor

copy1.append(99)
print(original)   # [1, 2, 3, 4] — unchanged
```

#### Lists in Lists (Matrices)

```python
matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

matrix[0]      # [1, 2, 3]
matrix[1][2]   # 6 (row 1, column 2)
matrix[2][0]   # 7

# Iterate
for row in matrix:
    for item in row:
        print(item, end=" ")
    print()
```

---

### 3.2 Tuples

#### Creating Tuples

```python
empty = ()
empty = tuple()

single = (42,)    # NOTE: trailing comma required for single-element tuple!
single_wrong = (42)   # This is just the integer 42!

colors = ("red", "green", "blue")
mixed = (1, "hello", 3.14)

# Packing (parentheses optional)
coords = 10, 20, 30
```

#### Tuple Indexing, Slicing, and Immutability

```python
coords = (10, 20, 30, 40)

coords[0]     # 10
coords[-1]    # 40
coords[1:3]   # (20, 30)

# Tuples are IMMUTABLE
coords[0] = 99  # TypeError! Cannot modify tuple
```

#### Tuples vs. Lists

| Feature | List `[]` | Tuple `()` |
|---|---|---|
| Mutable | ✅ Yes | ❌ No |
| Indexing | ✅ Yes | ✅ Yes |
| Slicing | ✅ Yes | ✅ Yes |
| Ordering | ✅ Yes | ✅ Yes |
| Duplicates | ✅ Yes | ✅ Yes |
| Use as dict key | ❌ No | ✅ Yes |
| Performance | Slower | Faster |

```python
# Tuples inside lists
data = [(1, "Alice"), (2, "Bob"), (3, "Carol")]
for id, name in data:
    print(f"{id}: {name}")

# Lists inside tuples
record = ([1, 2, 3], [4, 5, 6])   # Tuple of lists
record[0].append(99)               # OK — modifying the LIST, not the tuple
```

#### Tuple Unpacking

```python
point = (10, 20)
x, y = point     # Unpack into variables
print(x, y)      # 10 20

# Swap values elegantly
a, b = 5, 10
a, b = b, a      # a=10, b=5

# Extended unpacking
first, *rest = (1, 2, 3, 4, 5)
print(first)   # 1
print(rest)    # [2, 3, 4, 5]
```

---

### 3.3 Dictionaries

#### Building Dictionaries

```python
# Empty dictionary
empty = {}
empty = dict()

# With initial values
person = {"name": "Alice", "age": 30, "city": "Boston"}

# dict() constructor
person = dict(name="Alice", age=30, city="Boston")
```

#### Indexing and Modifying

```python
person = {"name": "Alice", "age": 30}

# Access by key
person["name"]    # "Alice"
person.get("age") # 30
person.get("email", "N/A")   # "N/A" — default if key missing

# Add / update
person["email"] = "alice@example.com"  # Add new key
person["age"] = 31                      # Update existing key

# Remove
del person["email"]          # Delete key-value pair
value = person.pop("age")    # Remove and return value
person.popitem()             # Remove and return last item (Python 3.7+)
```

#### Checking Key Existence

```python
person = {"name": "Alice", "age": 30}

"name" in person      # True
"email" in person     # False
"email" not in person # True
```

#### Dictionary Methods

```python
person = {"name": "Alice", "age": 30, "city": "Boston"}

# Keys, values, and items
person.keys()    # dict_keys(['name', 'age', 'city'])
person.values()  # dict_values(['Alice', 30, 'Boston'])
person.items()   # dict_items([('name', 'Alice'), ('age', 30), ...])
```

#### Iterating Through Dictionaries

```python
person = {"name": "Alice", "age": 30, "city": "Boston"}

# Iterate over keys (default)
for key in person:
    print(key)

# Iterate over keys explicitly
for key in person.keys():
    print(key)

# Iterate over values
for value in person.values():
    print(value)

# Iterate over key-value pairs
for key, value in person.items():
    print(f"{key}: {value}")
```

---

### 3.4 Strings (in Collections Context)

#### Constructing Strings

```python
single = 'Hello'
double = "World"
triple_single = '''Multi
line string'''
triple_double = """Also
multi-line"""
```

#### Escaping

```python
# Backslash escapes
"He said \"Hello\""    # He said "Hello"
'It\'s working'        # It's working
"Line1\nLine2"         # Line1 (newline) Line2
"Tab\there"            # Tab    here
"Backslash: \\"        # Backslash: \

# Raw strings (escape sequences ignored)
r"C:\Users\name"       # C:\Users\name (no escaping)
r'\n is not a newline' # \n is not a newline
```

#### Quotes Inside Strings

```python
# Mix quote types
"It's a beautiful day"     # Single quote inside double
'She said "hello"'         # Double quote inside single
"She said \"hello\""       # Escaped double quote
'It\'s a "mix"'            # Both types with escape
```

#### Multi-line Strings

```python
long_text = """This is line one.
This is line two.
This is line three."""

# Alternative using line continuation
long_text = (
    "This is part one "
    "and this is part two."  # String literal concatenation
)
```

#### Basic String Functions and Methods

```python
text = "Hello, World!"

# Length
len(text)              # 13

# Case
text.upper()           # "HELLO, WORLD!"
text.lower()           # "hello, world!"

# Stripping whitespace
"  hello  ".strip()    # "hello"
"  hello  ".lstrip()   # "hello  "
"  hello  ".rstrip()   # "  hello"

# Finding and replacing
text.find("World")     # 7
text.replace("World", "Python")  # "Hello, Python!"

# Splitting and joining
"a,b,c".split(",")     # ["a", "b", "c"]
",".join(["a", "b", "c"])  # "a,b,c"

# Checking content
"hello".startswith("he")  # True
"hello".endswith("lo")    # True
"123".isdigit()            # True
"abc".isalpha()            # True
"abc123".isalnum()         # True

# Formatting
f"Name: {'Alice'}, Age: {30}"  # f-strings (Python 3.6+)
"Name: {}, Age: {}".format("Alice", 30)  # .format()
"Name: %s, Age: %d" % ("Alice", 30)     # % formatting (older)
```

---

## Section 4: Functions and Exceptions (28%)

### 4.1 Decompose Code Using Functions

#### Defining and Invoking Functions

```python
# Define
def greet():
    print("Hello, World!")

# Invoke
greet()   # Hello, World!

# With parameters and return
def add(a, b):
    return a + b

result = add(3, 5)   # 8
```

#### The return Keyword

```python
def square(x):
    return x ** 2

def check_even(n):
    return n % 2 == 0   # Returns True or False

# Multiple return values (as tuple)
def min_max(numbers):
    return min(numbers), max(numbers)

low, high = min_max([3, 1, 4, 1, 5, 9])
print(low, high)   # 1 9
```

#### The None Keyword

```python
# Functions without return implicitly return None
def no_return():
    print("I don't return anything")

result = no_return()
print(result)       # None

# None is falsy
if result is None:
    print("Got None")

if not result:
    print("None is falsy")

# None vs False vs 0 vs ""
print(None == False)   # False
print(None is None)    # True
```

#### Generators

```python
# Generator — uses yield instead of return
def countdown(n):
    while n > 0:
        yield n
        n -= 1

for num in countdown(5):
    print(num)   # 5 4 3 2 1

# Generator expressions (like list comprehensions but lazy)
gen = (x**2 for x in range(10))
print(next(gen))   # 0
print(next(gen))   # 1
print(list(gen))   # [4, 9, 16, 25, 36, 49, 64, 81] — remaining values
```

#### Recursion

```python
# Recursive function — calls itself
def factorial(n):
    if n == 0:           # Base case (required to stop!)
        return 1
    return n * factorial(n - 1)  # Recursive call

print(factorial(5))   # 120

# Trace:
# factorial(5) = 5 * factorial(4)
# factorial(4) = 4 * factorial(3)
# factorial(3) = 3 * factorial(2)
# factorial(2) = 2 * factorial(1)
# factorial(1) = 1 * factorial(0)
# factorial(0) = 1  ← base case

# Fibonacci
def fib(n):
    if n <= 1:
        return n
    return fib(n-1) + fib(n-2)
```

---

### 4.2 Organizing Function Environments

#### Parameters vs. Arguments

```python
def greet(name, greeting):   # name, greeting are PARAMETERS
    print(f"{greeting}, {name}!")

greet("Alice", "Hello")      # "Alice", "Hello" are ARGUMENTS
```

#### Positional, Keyword, and Mixed Argument Passing

```python
def describe(name, age, city):
    print(f"{name} is {age} years old, from {city}")

# Positional — order matters
describe("Alice", 30, "Boston")

# Keyword — order doesn't matter
describe(city="Boston", name="Alice", age=30)

# Mixed — positional must come first
describe("Alice", city="Boston", age=30)
```

#### Default Parameter Values

```python
def greet(name, greeting="Hello"):
    print(f"{greeting}, {name}!")

greet("Alice")              # Hello, Alice! (uses default)
greet("Bob", "Good morning") # Good morning, Bob! (overrides default)

# Important: default values are evaluated ONCE at function definition
def append_to(item, lst=[]):   # Mutable default — DANGEROUS!
    lst.append(item)
    return lst

print(append_to(1))  # [1]
print(append_to(2))  # [1, 2] — unexpected! Same list reused

# Correct way:
def append_to(item, lst=None):
    if lst is None:
        lst = []
    lst.append(item)
    return lst
```

#### Name Scopes

```python
# LEGB Rule: Local → Enclosing → Global → Built-in

x = "global"   # Global scope

def outer():
    x = "enclosing"   # Enclosing scope
    
    def inner():
        x = "local"   # Local scope
        print(x)      # "local"
    
    inner()
    print(x)   # "enclosing"

outer()
print(x)       # "global"
```

#### Name Hiding (Shadowing)

```python
len = 5           # Shadows the built-in len()!
print(len)        # 5
print(len([1,2])) # TypeError! len is now an int

# Fix:
del len           # Remove shadow, restore built-in
print(len([1,2])) # 2
```

#### The global Keyword

```python
count = 0   # Global variable

def increment():
    global count        # Declare we're modifying global
    count += 1

increment()
increment()
print(count)   # 2

# Without global:
def bad_increment():
    count += 1   # UnboundLocalError! Python sees count as local
```

---

### 4.3 Python Built-In Exceptions Hierarchy

```
BaseException
├── SystemExit               ← sys.exit() raises this
├── KeyboardInterrupt        ← Ctrl+C raises this
└── Exception                ← Base for "normal" exceptions
    ├── ArithmeticError      ← Math errors
    │   ├── ZeroDivisionError
    │   ├── OverflowError
    │   └── FloatingPointError
    ├── LookupError          ← Index/key problems
    │   ├── IndexError       ← list[99] on short list
    │   └── KeyError         ← dict["missing_key"]
    ├── TypeError            ← Wrong type for operation
    ├── ValueError           ← Right type, wrong value
    ├── NameError            ← Undefined variable name
    ├── AttributeError       ← obj.nonexistent_attr
    ├── ImportError
    │   └── ModuleNotFoundError
    └── OSError
        ├── FileNotFoundError
        └── PermissionError
```

**Key examples:**

```python
1 / 0              # ZeroDivisionError
[1,2,3][10]        # IndexError
{"a": 1}["b"]      # KeyError
"2" + 2            # TypeError
int("hello")       # ValueError
undefined_var      # NameError
```

---

### 4.4 Basics of Python Exception Handling

#### try-except

```python
try:
    result = int(input("Enter a number: "))
    print(10 / result)
except ValueError:
    print("That's not a valid integer!")
except ZeroDivisionError:
    print("Can't divide by zero!")
```

#### try-except Exception (Catch-All)

```python
try:
    # risky code
    x = int("bad")
except Exception as e:
    print(f"Something went wrong: {e}")
    print(f"Error type: {type(e).__name__}")
```

#### Ordering the except Branches

Specific exceptions must come **before** general ones:

```python
# CORRECT — specific before general
try:
    result = 1 / 0
except ZeroDivisionError:
    print("Division by zero")
except ArithmeticError:
    print("Math error")
except Exception:
    print("Some error")

# WRONG — unreachable code
try:
    result = 1 / 0
except Exception:       # Catches everything first!
    print("Some error")
except ZeroDivisionError:  # Never reached
    print("Division by zero")
```

#### else and finally

```python
try:
    x = int(input("Enter positive number: "))
    result = 10 / x
except ValueError:
    print("Not a number")
except ZeroDivisionError:
    print("Can't be zero")
else:
    # Runs only if NO exception occurred
    print(f"Result: {result}")
finally:
    # ALWAYS runs, exception or not
    print("Done.")
```

#### Propagating Exceptions Through Function Boundaries

```python
def divide(a, b):
    return a / b   # ZeroDivisionError propagates if b=0

def calculate():
    return divide(10, 0)   # Exception propagates up

try:
    result = calculate()
except ZeroDivisionError:
    print("Caught in outer block")   # Caught here!
```

#### Delegating Responsibility

```python
def read_number():
    return int(input("Enter a number: "))   # ValueError may raise

def main():
    try:
        n = read_number()   # read_number doesn't handle it
        print(n * 2)
    except ValueError:
        print("Please enter a valid integer!")   # main handles it

# The caller decides what to do with the exception
```

---

## Study Tips and Practice Recommendations

### Key Areas to Prioritize

1. **Control Flow (29%)** — Largest section; master all loop forms including for-else/while-else
2. **Functions & Exceptions (28%)** — Second largest; focus on scope, arguments, and exception ordering
3. **Data Collections (25%)** — Know list/dict/tuple differences cold
4. **Fundamentals (18%)** — Make sure operator precedence and type casting are solid

### Common Pitfalls on the Exam

- Forgetting that `input()` returns a **string** — always cast!
- `int(3.9)` → `3`, not `4` (truncates, doesn't round)
- `0.1 + 0.2 != 0.3` — floating point isn't exact
- `(42)` is an int; `(42,)` is a tuple
- `list.sort()` returns `None`; `sorted(list)` returns a new list
- Alias vs. copy: `b = a` doesn't copy a list
- `global` keyword is needed to *assign* to a global; not needed to *read* it
- `except` branches must go specific → general or you get unreachable code

### Quick Reference — Built-in Functions to Know

```python
print()       # Output
input()       # Input (returns string)
int()         # Cast to integer
float()       # Cast to float
str()         # Cast to string
bool()        # Cast to boolean
len()         # Length of sequence
range()       # Number sequence generator
type()        # Get type of object
sorted()      # Return sorted copy
list()        # Create/convert to list
tuple()       # Create/convert to tuple
dict()        # Create/convert to dict
min()         # Minimum value
max()         # Maximum value
sum()         # Sum of iterable
abs()         # Absolute value
round()       # Round number
enumerate()   # Index + value pairs
```

### Operator Precedence — Quick Cheat Sheet

```
** > (unary +/-) > * / // % > + - > << >> > & > ^ > | > comparisons > not > and > or
```

### Before the Exam

- Write and run every code example in this guide
- Practice tracing code by hand (know what `print()` outputs before running)
- Drill list/dict/tuple indexing until it's automatic
- Test yourself on operator precedence edge cases
- Know the exception hierarchy order by heart
- Review for-else and while-else (commonly tested, easy to forget)

---

**Good luck with your PCEP exam! 🐍**
