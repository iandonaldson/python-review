# Python Basics Guide

A comprehensive guide covering fundamental Python concepts with examples and outputs.

## Table of Contents

1. [Syntax](#syntax)
2. [Comments](#comments)
3. [Variables](#variables)
4. [Data Types](#data-types)
5. [Numbers](#numbers)
6. [Casting](#casting)
7. [Strings](#strings)
8. [Booleans](#booleans)
9. [Operators](#operators)
10. [Lists](#lists)
11. [Tuples](#tuples)
12. [Sets](#sets)
13. [Dictionaries](#dictionaries)
14. [If...Else](#ifelse)
15. [While Loops](#while-loops)
16. [For Loops](#for-loops)
17. [Functions](#functions)
18. [Lambda](#lambda)
19. [Arrays](#arrays)
20. [Classes/Objects](#classesobjects)
21. [Inheritance](#inheritance)
22. [Iterators](#iterators)
23. [Polymorphism](#polymorphism)
24. [Scope](#scope)
25. [Modules](#modules)
26. [Dates](#dates)
27. [Math](#math)
28. [JSON](#json)
29. [RegEx](#regex)
30. [PIP](#pip)
31. [Try...Except](#tryexcept)
32. [User Input](#user-input)
33. [String Formatting](#string-formatting)
34. [File Handling](#file-handling)
35. [Virtual Environment](#virtual-environment)

---

## Syntax

Python uses indentation to define code blocks, making it readable and clean. Statements end naturally at the end of a line.

```python
# Simple print statement
print("Hello, Python!")

# Indentation for code blocks
if True:
    print("This is indented")
    print("Still in the same block")
```

**Output:**
```
Hello, Python!
This is indented
Still in the same block
```

---

## Comments

Comments help document code and are ignored during execution. Use `#` for single-line and triple quotes for multi-line comments.

```python
# This is a single-line comment

"""
This is a multi-line comment
spanning multiple lines
"""

print("Comments don't affect execution")  # Inline comment
```

**Output:**
```
Comments don't affect execution
```

---

## Variables

Variables store data values. Python is dynamically typed - no declaration needed, just assign a value.

### Variable Names

```python
# Valid variable names
my_var = "valid"
_private = "valid"
var123 = "valid"
myVar = "valid"
MYVAR = "valid"

# Variables are case-sensitive
name = "Alice"
Name = "Bob"
print(f"name: {name}, Name: {Name}")
```

**Output:**
```
name: Alice, Name: Bob
```

### Assigning Multiple Values

```python
# Multiple variables in one line
x, y, z = "Red", "Green", "Blue"
print(f"x={x}, y={y}, z={z}")

# Same value to multiple variables
a = b = c = 100
print(f"a={a}, b={b}, c={c}")

# Unpacking a list
colors = ["red", "green", "blue"]
r, g, b = colors
print(f"r={r}, g={g}, b={b}")
```

**Output:**
```
x=Red, y=Green, z=Blue
a=100, b=100, c=100
r=red, g=green, b=blue
```

### Output Variables

```python
x = "Python"
y = "is"
z = "awesome"

# Multiple ways to output
print(x, y, z)
print(x + " " + y + " " + z)

# Mixing types requires conversion
age = 30
print("Age: " + str(age))
```

**Output:**
```
Python is awesome
Python is awesome
Age: 30
```

### Global Variables

```python
# Global variable
global_text = "I'm global"

def my_function():
    # Local variable
    local_text = "I'm local"
    print(global_text)
    print(local_text)

my_function()
print(global_text)
# print(local_text)  # This would cause an error
```

**Output:**
```
I'm global
I'm local
I'm global
```

---

## Data Types

Python has several built-in data types including numeric, sequence, mapping, and boolean types.

```python
# Numeric types
integer_num = 42
float_num = 3.14
complex_num = 2 + 3j

# Sequence types
my_string = "Hello"
my_list = [1, 2, 3]
my_tuple = (4, 5, 6)

# Mapping type
my_dict = {"key": "value"}

# Boolean
my_bool = True

print(type(integer_num), type(float_num), type(my_list), type(my_dict))
```

**Output:**
```
<class 'int'> <class 'float'> <class 'list'> <class 'dict'>
```

---

## Numbers

Python supports integers, floats, and complex numbers with various mathematical operations.

### Numeric Types

```python
x = 10      # int
y = 3.5     # float
z = 2 + 4j  # complex

print(f"Integer: {x}, type: {type(x)}")
print(f"Float: {y}, type: {type(y)}")
print(f"Complex: {z}, type: {type(z)}")
print(f"Addition: {x + y}")
print(f"Power: {x ** 2}")
```

**Output:**
```
Integer: 10, type: <class 'int'>
Float: 3.5, type: <class 'float'>
Complex: (2+4j), type: <class 'complex'>
Addition: 13.5
Power: 100
```

### Type Conversion

```python
a = 5       # int
b = 2.8     # float
c = 1 + 2j  # complex

# Convert int to float
x = float(a)
print(f"int to float: {x}, type: {type(x)}")

# Convert float to int (truncates)
y = int(b)
print(f"float to int: {y}, type: {type(y)}")

# Cannot convert complex to int/float
```

**Output:**
```
int to float: 5.0, type: <class 'float'>
float to int: 2, type: <class 'int'>
```

### Random Numbers

```python
import random

print(f"Random between 1-10: {random.randrange(1, 11)}")
print(f"Random float 0-1: {random.random():.4f}")
print(f"Random choice: {random.choice([1, 2, 3, 4, 5])}")
```

**Output:**
```
Random between 1-10: 7
Random float 0-1: 0.4237
Random choice: 3
```

---

## Casting

Convert between data types using constructor functions like `int()`, `float()`, and `str()`.

```python
x = "123"
y = 45.8
z = 100

int_x = int(x)
float_y = float(z)
str_y = str(y)

print(f"String to int: {int_x}, type: {type(int_x)}")
print(f"Int to float: {float_y}, type: {type(float_y)}")
print(f"Float to string: {str_y}, type: {type(str_y)}")
```

**Output:**
```
String to int: 123, type: <class 'int'>
Int to float: 100.0, type: <class 'float'>
Float to string: 45.8, type: <class 'str'>
```

---

## Strings

Strings are sequences of characters enclosed in quotes. They support indexing, slicing, and many methods.

### String Literals and Multiline Strings

```python
# Single or double quotes
single = 'Hello'
double = "World"

# Multiline strings
multiline = """This is a
multiline
string"""

print(single)
print(double)
print(multiline)
```

**Output:**
```
Hello
World
This is a
multiline
string
```

### Strings as Arrays

```python
text = "Python"

print(f"First character: {text[0]}")
print(f"Last character: {text[-1]}")
print(f"Length: {len(text)}")

# Loop through string
for char in "ABC":
    print(char)
```

**Output:**
```
First character: P
Last character: n
Length: 6
A
B
C
```

### Slicing Strings

```python
text = "Hello, World!"

print(f"Characters 2-5: {text[2:5]}")
print(f"From start to 5: {text[:5]}")
print(f"From 7 to end: {text[7:]}")
print(f"Negative indexing: {text[-5:-2]}")
```

**Output:**
```
Characters 2-5: llo
From start to 5: Hello
From 7 to end: World!
Negative indexing: orl
```

### Modifying and Formatting Strings

```python
text = "  Python Programming  "

print(f"Uppercase: {text.upper()}")
print(f"Lowercase: {text.lower()}")
print(f"Strip whitespace: '{text.strip()}'")
print(f"Replace: {text.replace('Python', 'Java')}")
print(f"Split: {text.split()}")
```

**Output:**
```
Uppercase:   PYTHON PROGRAMMING  
Lowercase:   python programming  
Strip whitespace: 'Python Programming'
Replace:   Java Programming  
Split: ['Python', 'Programming']
```

### String Concatenation

```python
a = "Hello"
b = "World"

print(a + " " + b)
print(a, b)

# Cannot concatenate string and number directly
age = 25
text = "Age is " + str(age)
print(text)
```

**Output:**
```
Hello World
Hello World
Age is 25
```

### Escape Characters

```python
# Common escape characters
print("Line 1\nLine 2")  # Newline
print("Tab\tSeparated")  # Tab
print("She said \"Hello\"")  # Quote
print("Path: C:\\Users\\name")  # Backslash
```

**Output:**
```
Line 1
Line 2
Tab	Separated
She said "Hello"
Path: C:\Users\name
```

### String Methods

```python
text = "hello world"

print(f"Capitalize: {text.capitalize()}")
print(f"Title case: {text.title()}")
print(f"Count 'o': {text.count('o')}")
print(f"Starts with 'hello': {text.startswith('hello')}")
print(f"Ends with 'world': {text.endswith('world')}")
print(f"Find 'world': {text.find('world')}")
print(f"Is alphanumeric: {text.isalnum()}")
print(f"Is alphabetic: {'hello'.isalpha()}")
```

**Output:**
```
Capitalize: Hello world
Title case: Hello World
Count 'o': 2
Starts with 'hello': True
Ends with 'world': True
Find 'world': 6
Is alphanumeric: False
Is alphabetic: True
```

---

## Booleans

Booleans represent `True` or `False` values, essential for conditional logic.

```python
a = True
b = False

print(f"a is {a}")
print(f"b is {b}")
print(f"10 > 5: {10 > 5}")
print(f"5 == 10: {5 == 10}")
print(f"bool(0): {bool(0)}")
print(f"bool('text'): {bool('text')}")
```

**Output:**
```
a is True
b is False
10 > 5: True
5 == 10: False
bool(0): False
bool('text'): True
```

---

## Operators

Python supports arithmetic, assignment, comparison, logical, identity, membership, and bitwise operators.

### Arithmetic Operators

```python
x = 10
y = 3

print(f"Addition: {x + y}")
print(f"Subtraction: {x - y}")
print(f"Multiplication: {x * y}")
print(f"Division: {x / y}")
print(f"Floor division: {x // y}")
print(f"Modulus: {x % y}")
print(f"Exponentiation: {x ** y}")
```

**Output:**
```
Addition: 13
Subtraction: 7
Multiplication: 30
Division: 3.3333333333333335
Floor division: 3
Modulus: 1
Exponentiation: 1000
```

### Assignment Operators

```python
x = 5
print(f"x = {x}")

x += 3  # x = x + 3
print(f"x += 3: {x}")

x -= 2  # x = x - 2
print(f"x -= 2: {x}")

x *= 2  # x = x * 2
print(f"x *= 2: {x}")

x //= 3  # x = x // 3
print(f"x //= 3: {x}")
```

**Output:**
```
x = 5
x += 3: 8
x -= 2: 6
x *= 2: 12
x //= 3: 4
```

### Comparison Operators

```python
a = 10
b = 5

print(f"a == b: {a == b}")
print(f"a != b: {a != b}")
print(f"a > b: {a > b}")
print(f"a < b: {a < b}")
print(f"a >= b: {a >= b}")
print(f"a <= b: {a <= b}")
```

**Output:**
```
a == b: False
a != b: True
a > b: True
a < b: False
a >= b: True
a <= b: False
```

### Logical Operators

```python
x = True
y = False

print(f"x and y: {x and y}")
print(f"x or y: {x or y}")
print(f"not x: {not x}")
print(f"(5 > 3) and (8 > 5): {(5 > 3) and (8 > 5)}")
```

**Output:**
```
x and y: False
x or y: True
not x: False
(5 > 3) and (8 > 5): True
```

### Identity Operators

```python
a = [1, 2, 3]
b = [1, 2, 3]
c = a

print(f"a is c: {a is c}")
print(f"a is b: {a is b}")
print(f"a == b: {a == b}")
print(f"a is not b: {a is not b}")

x = 5
y = 5
print(f"x is y: {x is y}")  # Small integers are cached
```

**Output:**
```
a is c: True
a is b: False
a == b: True
a is not b: True
x is y: True
```

### Membership Operators

```python
fruits = ["apple", "banana", "cherry"]
text = "Hello World"

print(f"'banana' in fruits: {'banana' in fruits}")
print(f"'orange' in fruits: {'orange' in fruits}")
print(f"'orange' not in fruits: {'orange' not in fruits}")
print(f"'World' in text: {'World' in text}")
```

**Output:**
```
'banana' in fruits: True
'orange' in fruits: False
'orange' not in fruits: True
'World' in text: True
```

### Bitwise Operators

```python
a = 10  # Binary: 1010
b = 4   # Binary: 0100

print(f"a & b (AND): {a & b}")
print(f"a | b (OR): {a | b}")
print(f"a ^ b (XOR): {a ^ b}")
print(f"~a (NOT): {~a}")
print(f"a << 2 (Left shift): {a << 2}")
print(f"a >> 2 (Right shift): {a >> 2}")
```

**Output:**
```
a & b (AND): 0
a | b (OR): 14
a ^ b (XOR): 14
~a (NOT): -11
a << 2 (Left shift): 40
a >> 2 (Right shift): 2
```

---

## Lists

Lists are ordered, mutable collections that can contain mixed data types.

### Creating and Accessing Lists

```python
fruits = ["apple", "banana", "cherry"]
numbers = [1, 2, 3, 4, 5]
mixed = [1, "hello", 3.14, True]

print(f"Fruits: {fruits}")
print(f"First fruit: {fruits[0]}")
print(f"Last fruit: {fruits[-1]}")
print(f"Slice [1:3]: {fruits[1:3]}")
print(f"List length: {len(fruits)}")
```

**Output:**
```
Fruits: ['apple', 'banana', 'cherry']
First fruit: apple
Last fruit: cherry
Slice [1:3]: ['banana', 'cherry']
List length: 3
```

### Modifying Lists

```python
fruits = ["apple", "banana", "cherry"]

# Change item
fruits[1] = "blueberry"
print(f"After change: {fruits}")

# Add items
fruits.append("orange")
print(f"After append: {fruits}")

fruits.insert(1, "kiwi")
print(f"After insert: {fruits}")

# Remove items
fruits.remove("cherry")
print(f"After remove: {fruits}")

popped = fruits.pop()
print(f"Popped: {popped}, Remaining: {fruits}")

del fruits[0]
print(f"After del: {fruits}")
```

**Output:**
```
After change: ['apple', 'blueberry', 'cherry']
After append: ['apple', 'blueberry', 'cherry', 'orange']
After insert: ['apple', 'kiwi', 'blueberry', 'cherry', 'orange']
After remove: ['apple', 'kiwi', 'blueberry', 'orange']
Popped: orange, Remaining: ['apple', 'kiwi', 'blueberry']
After del: ['kiwi', 'blueberry']
```

### List Comprehension

```python
# Create list of squares
squares = [x**2 for x in range(6)]
print(f"Squares: {squares}")

# With condition
evens = [x for x in range(10) if x % 2 == 0]
print(f"Evens: {evens}")

# Transform strings
fruits = ["apple", "banana", "cherry"]
upper_fruits = [fruit.upper() for fruit in fruits]
print(f"Uppercase: {upper_fruits}")
```

**Output:**
```
Squares: [0, 1, 4, 9, 16, 25]
Evens: [0, 2, 4, 6, 8]
Uppercase: ['APPLE', 'BANANA', 'CHERRY']
```

### Sorting Lists

```python
numbers = [5, 2, 8, 1, 9]
fruits = ["banana", "apple", "cherry"]

# Sort ascending
numbers.sort()
print(f"Sorted numbers: {numbers}")

# Sort descending
fruits.sort(reverse=True)
print(f"Sorted fruits (desc): {fruits}")

# Sorted() returns new list
original = [3, 1, 4, 1, 5]
sorted_list = sorted(original)
print(f"Original: {original}, Sorted: {sorted_list}")
```

**Output:**
```
Sorted numbers: [1, 2, 5, 8, 9]
Sorted fruits (desc): ['cherry', 'banana', 'apple']
Original: [3, 1, 4, 1, 5], Sorted: [1, 1, 3, 4, 5]
```

### Copying Lists

```python
original = [1, 2, 3]

# Wrong way - creates reference
ref = original
ref.append(4)
print(f"Original after ref change: {original}")

# Right way - copy()
copy1 = original.copy()
copy1.append(5)
print(f"Original: {original}, Copy: {copy1}")

# Using list()
copy2 = list(original)
print(f"Copy2: {copy2}")

# Using slicing
copy3 = original[:]
print(f"Copy3: {copy3}")
```

**Output:**
```
Original after ref change: [1, 2, 3, 4]
Original: [1, 2, 3, 4], Copy: [1, 2, 3, 4, 5]
Copy2: [1, 2, 3, 4]
Copy3: [1, 2, 3, 4]
```

### Joining Lists

```python
list1 = [1, 2, 3]
list2 = [4, 5, 6]

# Using +
list3 = list1 + list2
print(f"Using +: {list3}")

# Using extend()
list1.extend(list2)
print(f"Using extend: {list1}")

# Using append (adds as single element)
test = [1, 2]
test.append([3, 4])
print(f"Using append: {test}")
```

**Output:**
```
Using +: [1, 2, 3, 4, 5, 6]
Using extend: [1, 2, 3, 4, 5, 6]
Using append: [1, 2, [3, 4]]
```

---

## Tuples

Tuples are ordered, immutable collections defined with parentheses.

### Creating and Accessing Tuples

```python
coordinates = (10, 20, 30)
single_item = (42,)
empty_tuple = ()

print(f"Tuple: {coordinates}")
print(f"First element: {coordinates[0]}")
print(f"Last element: {coordinates[-1]}")
print(f"Slice: {coordinates[1:]}")
print(f"Length: {len(coordinates)}")
```

**Output:**
```
Tuple: (10, 20, 30)
First element: 10
Last element: 30
Slice: (20, 30)
Length: 3
```

### Updating Tuples

```python
# Tuples are immutable, but can convert to list
original = (1, 2, 3)
temp_list = list(original)
temp_list.append(4)
updated = tuple(temp_list)

print(f"Original: {original}")
print(f"Updated: {updated}")

# Can concatenate tuples
tuple1 = (1, 2)
tuple2 = (3, 4)
combined = tuple1 + tuple2
print(f"Combined: {combined}")
```

**Output:**
```
Original: (1, 2, 3)
Updated: (1, 2, 3, 4)
Combined: (1, 2, 3, 4)
```

### Unpacking Tuples

```python
# Basic unpacking
fruits = ("apple", "banana", "cherry")
(red, yellow, pink) = fruits
print(f"red={red}, yellow={yellow}, pink={pink}")

# Using asterisk for remaining items
numbers = (1, 2, 3, 4, 5)
(first, second, *rest) = numbers
print(f"first={first}, second={second}, rest={rest}")

# Asterisk in middle
(first, *middle, last) = numbers
print(f"first={first}, middle={middle}, last={last}")
```

**Output:**
```
red=apple, yellow=banana, pink=cherry
first=1, second=2, rest=[3, 4, 5]
first=1, middle=[2, 3, 4], last=5
```

### Tuple Methods and Operations

```python
numbers = (1, 2, 2, 3, 4, 2)

print(f"Count of 2: {numbers.count(2)}")
print(f"Index of 3: {numbers.index(3)}")
print(f"Max: {max(numbers)}")
print(f"Min: {min(numbers)}")
print(f"Sum: {sum(numbers)}")

# Looping through tuple
for num in (10, 20, 30):
    print(f"Value: {num}")
```

**Output:**
```
Count of 2: 3
Index of 3: 3
Max: 4
Min: 1
Sum: 14
Value: 10
Value: 20
Value: 30
```

### Joining Tuples

```python
tuple1 = (1, 2, 3)
tuple2 = (4, 5, 6)

# Using + operator
joined = tuple1 + tuple2
print(f"Joined: {joined}")

# Multiply tuple
repeated = tuple1 * 2
print(f"Repeated: {repeated}")
```

**Output:**
```
Joined: (1, 2, 3, 4, 5, 6)
Repeated: (1, 2, 3, 1, 2, 3)
```

---

## Sets

Sets are unordered collections of unique elements, useful for mathematical operations.

### Creating and Accessing Sets

```python
fruits = {"apple", "banana", "cherry"}
numbers = {1, 2, 3, 4, 5}

print(f"Fruits: {fruits}")
print(f"Length: {len(fruits)}")
print(f"'apple' in fruits: {'apple' in fruits}")

# Cannot access by index, must loop
for fruit in fruits:
    print(f"- {fruit}")
```

**Output:**
```
Fruits: {'apple', 'banana', 'cherry'}
Length: 3
'apple' in fruits: True
- apple
- banana
- cherry
```

### Adding and Removing Items

```python
fruits = {"apple", "banana", "cherry"}

# Add single item
fruits.add("orange")
print(f"After add: {fruits}")

# Add multiple items
fruits.update(["mango", "grapes"])
print(f"After update: {fruits}")

# Remove items
fruits.remove("banana")
print(f"After remove: {fruits}")

# Discard (doesn't error if not found)
fruits.discard("kiwi")
print(f"After discard: {fruits}")

# Pop random item
popped = fruits.pop()
print(f"Popped: {popped}, Remaining: {fruits}")
```

**Output:**
```
After add: {'apple', 'banana', 'cherry', 'orange'}
After update: {'apple', 'banana', 'cherry', 'orange', 'mango', 'grapes'}
After remove: {'apple', 'cherry', 'orange', 'mango', 'grapes'}
After discard: {'apple', 'cherry', 'orange', 'mango', 'grapes'}
Popped: apple, Remaining: {'cherry', 'orange', 'mango', 'grapes'}
```

### Set Operations

```python
set1 = {1, 2, 3, 4}
set2 = {3, 4, 5, 6}

print(f"Set 1: {set1}")
print(f"Set 2: {set2}")

# Union
print(f"Union (|): {set1 | set2}")
print(f"Union method: {set1.union(set2)}")

# Intersection
print(f"Intersection (&): {set1 & set2}")
print(f"Intersection method: {set1.intersection(set2)}")

# Difference
print(f"Difference (-): {set1 - set2}")
print(f"Difference method: {set1.difference(set2)}")

# Symmetric difference
print(f"Symmetric diff (^): {set1 ^ set2}")
print(f"Symmetric method: {set1.symmetric_difference(set2)}")
```

**Output:**
```
Set 1: {1, 2, 3, 4}
Set 2: {3, 4, 5, 6}
Union (|): {1, 2, 3, 4, 5, 6}
Union method: {1, 2, 3, 4, 5, 6}
Intersection (&): {3, 4}
Intersection method: {3, 4}
Difference (-): {1, 2}
Difference method: {1, 2}
Symmetric diff (^): {1, 2, 5, 6}
Symmetric method: {1, 2, 5, 6}
```

### Set Comparison Methods

```python
set1 = {1, 2, 3}
set2 = {1, 2, 3, 4, 5}
set3 = {1, 2, 3}

print(f"set1 is subset of set2: {set1.issubset(set2)}")
print(f"set2 is superset of set1: {set2.issuperset(set1)}")
print(f"set1 and set3 disjoint: {set1.isdisjoint(set3)}")
print(f"set1 == set3: {set1 == set3}")
```

**Output:**
```
set1 is subset of set2: True
set2 is superset of set1: True
set1 and set3 disjoint: False
set1 == set3: True
```

---

## Dictionaries

Dictionaries store key-value pairs, providing fast lookup by key.

### Creating and Accessing Dictionaries

```python
person = {
    "name": "Bob",
    "age": 25,
    "city": "New York"
}

print(f"Person: {person}")
print(f"Name: {person['name']}")
print(f"Age: {person.get('age')}")
print(f"Job: {person.get('job', 'Not specified')}")
print(f"Length: {len(person)}")
```

**Output:**
```
Person: {'name': 'Bob', 'age': 25, 'city': 'New York'}
Name: Bob
Age: 25
Job: Not specified
Length: 3
```

### Modifying Dictionaries

```python
person = {"name": "Alice", "age": 30}

# Add/update items
person["city"] = "Boston"
person["age"] = 31
print(f"After update: {person}")

# Update multiple items
person.update({"job": "Engineer", "salary": 75000})
print(f"After multiple update: {person}")

# Remove items
person.pop("salary")
print(f"After pop: {person}")

del person["age"]
print(f"After del: {person}")
```

**Output:**
```
After update: {'name': 'Alice', 'age': 31, 'city': 'Boston'}
After multiple update: {'name': 'Alice', 'age': 31, 'city': 'Boston', 'job': 'Engineer', 'salary': 75000}
After pop: {'name': 'Alice', 'age': 31, 'city': 'Boston', 'job': 'Engineer'}
After del: {'name': 'Alice', 'city': 'Boston', 'job': 'Engineer'}
```

### Looping Through Dictionaries

```python
person = {"name": "Bob", "age": 25, "city": "NYC"}

# Loop through keys
for key in person:
    print(f"{key}: {person[key]}")

print("\nUsing items():")
# Loop through key-value pairs
for key, value in person.items():
    print(f"{key} = {value}")

print(f"\nKeys: {list(person.keys())}")
print(f"Values: {list(person.values())}")
```

**Output:**
```
name: Bob
age: 25
city: NYC

Using items():
name = Bob
age = 25
city = NYC

Keys: ['name', 'age', 'city']
Values: ['Bob', 25, 'NYC']
```

### Copying Dictionaries

```python
original = {"a": 1, "b": 2}

# Wrong way - creates reference
ref = original
ref["c"] = 3
print(f"Original after ref change: {original}")

# Right way - copy()
copy1 = original.copy()
copy1["d"] = 4
print(f"Original: {original}")
print(f"Copy1: {copy1}")

# Using dict()
copy2 = dict(original)
print(f"Copy2: {copy2}")
```

**Output:**
```
Original after ref change: {'a': 1, 'b': 2, 'c': 3}
Original: {'a': 1, 'b': 2, 'c': 3}
Copy1: {'a': 1, 'b': 2, 'c': 3, 'd': 4}
Copy2: {'a': 1, 'b': 2, 'c': 3}
```

### Nested Dictionaries

```python
family = {
    "child1": {
        "name": "Emma",
        "age": 5
    },
    "child2": {
        "name": "Liam",
        "age": 8
    }
}

print(f"Family: {family}")
print(f"Child1 name: {family['child1']['name']}")
print(f"Child2 age: {family['child2']['age']}")

# Loop through nested dict
for child, info in family.items():
    print(f"\n{child}:")
    for key, value in info.items():
        print(f"  {key}: {value}")
```

**Output:**
```
Family: {'child1': {'name': 'Emma', 'age': 5}, 'child2': {'name': 'Liam', 'age': 8}}
Child1 name: Emma
Child2 age: 8

child1:
  name: Emma
  age: 5

child2:
  name: Liam
  age: 8
```

---

## If...Else

Conditional statements control program flow based on boolean expressions.

### Basic If...Elif...Else

```python
temperature = 25

if temperature > 30:
    print("It's hot!")
elif temperature > 20:
    print("It's pleasant")
else:
    print("It's cold!")

# Simple if
if temperature > 0:
    print("Above freezing")
```

**Output:**
```
It's pleasant
Above freezing
```

### Short Hand If (Ternary Operator)

```python
age = 20
status = "Adult" if age >= 18 else "Minor"
print(f"Status: {status}")

# Short hand if without else
if age > 18: print("Adult")

# Multiple statements on one line (not recommended)
if age > 18: print("Adult"); print("Can vote")
```

**Output:**
```
Status: Adult
Adult
Adult
Can vote
```

### Logical Operators (and, or, not)

```python
age = 25
income = 50000

if age >= 18 and income > 30000:
    print("Eligible for loan")

if age < 18 or age > 65:
    print("Discounted ticket")
else:
    print("Regular price")

has_license = False
if not has_license:
    print("Cannot drive")
```

**Output:**
```
Eligible for loan
Regular price
Cannot drive
```

### Nested If Statements

```python
num = 15

if num > 0:
    print("Positive number")
    if num % 2 == 0:
        print("Even")
    else:
        print("Odd")
else:
    print("Not positive")

# Multiple conditions
score = 85
if score >= 90:
    grade = "A"
elif score >= 80:
    grade = "B"
elif score >= 70:
    grade = "C"
else:
    grade = "F"
print(f"Grade: {grade}")
```

**Output:**
```
Positive number
Odd
Grade: B
```

### Pass Statement

```python
x = 10

# Pass for empty if block
if x > 5:
    pass  # TODO: implement later

print("Program continues")
```

**Output:**
```
Program continues
```

---

## While Loops

While loops repeat code as long as a condition remains true.

### Basic While Loop

```python
count = 0

while count < 5:
    print(f"Count is: {count}")
    count += 1

print("Loop finished")
```

**Output:**
```
Count is: 0
Count is: 1
Count is: 2
Count is: 3
Count is: 4
Loop finished
```

### Break Statement

```python
# Exit loop early
i = 0
while i < 10:
    if i == 5:
        break
    print(f"i = {i}")
    i += 1

print("Exited at 5")

# Infinite loop with break
num = 0
while True:
    if num == 3:
        break
    print(f"Num: {num}")
    num += 1
```

**Output:**
```
i = 0
i = 1
i = 2
i = 3
i = 4
Exited at 5
Num: 0
Num: 1
Num: 2
```

### Continue Statement

```python
# Skip specific iterations
i = 0
while i < 5:
    i += 1
    if i == 3:
        continue
    print(f"i = {i}")

print("Skipped 3")
```

**Output:**
```
i = 1
i = 2
i = 4
i = 5
Skipped 3
```

### Else Clause

```python
# Else executes when condition becomes false
count = 0
while count < 3:
    print(f"Count: {count}")
    count += 1
else:
    print("Loop completed normally")

# Else doesn't execute with break
count = 0
while count < 10:
    if count == 3:
        break
    count += 1
else:
    print("This won't print")

print("Loop was broken")
```

**Output:**
```
Count: 0
Count: 1
Count: 2
Loop completed normally
Loop was broken
```

---

## For Loops

For loops iterate over sequences like lists, strings, or ranges.

### Basic For Loops

```python
# Loop through list
colors = ["red", "green", "blue"]
for color in colors:
    print(f"Color: {color}")

# Loop through string
for char in "Python":
    print(char)
```

**Output:**
```
Color: red
Color: green
Color: blue
P
y
t
h
o
n
```

### Range Function

```python
# Range with stop
for i in range(5):
    print(i, end=" ")

print("\n")

# Range with start and stop
for i in range(2, 6):
    print(i, end=" ")

print("\n")

# Range with step
for i in range(0, 10, 2):
    print(i, end=" ")

print()
```

**Output:**
```
0 1 2 3 4 

2 3 4 5 

0 2 4 6 8
```

### Break Statement

```python
# Exit loop early
for i in range(10):
    if i == 5:
        break
    print(f"i = {i}")

print("Loop broken at 5")
```

**Output:**
```
i = 0
i = 1
i = 2
i = 3
i = 4
Loop broken at 5
```

### Continue Statement

```python
# Skip specific iterations
for i in range(6):
    if i == 3:
        continue
    print(f"i = {i}")

print("Skipped 3")
```

**Output:**
```
i = 0
i = 1
i = 2
i = 4
i = 5
Skipped 3
```

### Else Clause

```python
# Else executes after normal loop completion
for i in range(3):
    print(f"i = {i}")
else:
    print("Loop completed")

# Else doesn't execute with break
for i in range(5):
    if i == 2:
        break
else:
    print("This won't print")

print("Loop was broken")
```

**Output:**
```
i = 0
i = 1
i = 2
Loop completed
Loop was broken
```

### Nested Loops

```python
# Loop within a loop
adj = ["red", "big"]
fruits = ["apple", "banana"]

for a in adj:
    for f in fruits:
        print(f"{a} {f}")

# Multiplication table
for i in range(1, 4):
    for j in range(1, 4):
        print(f"{i} x {j} = {i*j}")
    print()
```

**Output:**
```
red apple
red banana
big apple
big banana
1 x 1 = 1
1 x 2 = 2
1 x 3 = 3

2 x 1 = 2
2 x 2 = 4
2 x 3 = 6

3 x 1 = 3
3 x 2 = 6
3 x 3 = 9

```

### Pass Statement

```python
# Empty loop body
for x in range(5):
    pass  # Placeholder for future code

print("Loop with pass completed")
```

**Output:**
```
Loop with pass completed
```

### Enumerate and Zip

```python
# Enumerate for index and value
colors = ["red", "green", "blue"]
for idx, color in enumerate(colors):
    print(f"{idx}: {color}")

print()

# Zip for parallel iteration
names = ["Alice", "Bob", "Charlie"]
ages = [25, 30, 35]
for name, age in zip(names, ages):
    print(f"{name} is {age} years old")
```

**Output:**
```
0: red
1: green
2: blue

Alice is 25 years old
Bob is 30 years old
Charlie is 35 years old
```

---

## Functions

Functions are reusable blocks of code defined with the `def` keyword.

### Basic Functions

```python
def greet(name):
    return f"Hello, {name}!"

def add_numbers(a, b):
    return a + b

print(greet("Alice"))
print(f"Sum: {add_numbers(5, 3)}")
```

**Output:**
```
Hello, Alice!
Sum: 8
```

### Default Parameters

```python
def greet(name, greeting="Hello"):
    return f"{greeting}, {name}!"

print(greet("Alice"))
print(greet("Bob", "Hi"))

def power(base, exp=2):
    return base ** exp

print(f"5 squared: {power(5)}")
print(f"2 cubed: {power(2, 3)}")
```

**Output:**
```
Hello, Alice!
Hi, Bob!
5 squared: 25
2 cubed: 8
```

### Keyword Arguments

```python
def describe_person(name, age, city):
    return f"{name} is {age} years old and lives in {city}"

# Positional arguments
print(describe_person("Alice", 30, "Boston"))

# Keyword arguments (order doesn't matter)
print(describe_person(city="NYC", name="Bob", age=25))

# Mixed
print(describe_person("Charlie", city="LA", age=35))
```

**Output:**
```
Alice is 30 years old and lives in Boston
Bob is 25 years old and lives in NYC
Charlie is 35 years old and lives in LA
```

### Arbitrary Arguments (*args)

```python
def sum_all(*numbers):
    total = 0
    for num in numbers:
        total += num
    return total

print(f"Sum: {sum_all(1, 2, 3)}")
print(f"Sum: {sum_all(10, 20, 30, 40, 50)}")

def print_names(*names):
    for name in names:
        print(f"Hello, {name}")

print_names("Alice", "Bob", "Charlie")
```

**Output:**
```
Sum: 6
Sum: 150
Hello, Alice
Hello, Bob
Hello, Charlie
```

### Arbitrary Keyword Arguments (**kwargs)

```python
def print_info(**info):
    for key, value in info.items():
        print(f"{key}: {value}")

print_info(name="Alice", age=30, city="Boston")

print()

def create_profile(name, **details):
    print(f"Name: {name}")
    for key, value in details.items():
        print(f"{key}: {value}")

create_profile("Bob", age=25, job="Engineer", city="NYC")
```

**Output:**
```
name: Alice
age: 30
city: Boston

Name: Bob
age: 25
job: Engineer
city: NYC
```

### Return Values

```python
# Multiple return values
def get_stats(numbers):
    return min(numbers), max(numbers), sum(numbers)

min_val, max_val, total = get_stats([1, 2, 3, 4, 5])
print(f"Min: {min_val}, Max: {max_val}, Total: {total}")

# Return list
def get_evens(numbers):
    return [n for n in numbers if n % 2 == 0]

evens = get_evens([1, 2, 3, 4, 5, 6])
print(f"Evens: {evens}")
```

**Output:**
```
Min: 1, Max: 5, Total: 15
Evens: [2, 4, 6]
```

### Pass Statement

```python
def future_function():
    pass  # TODO: implement later

future_function()
print("Function with pass executed")
```

**Output:**
```
Function with pass executed
```

### Recursion

```python
# Factorial using recursion
def factorial(n):
    if n == 0 or n == 1:
        return 1
    return n * factorial(n - 1)

print(f"Factorial of 5: {factorial(5)}")

# Fibonacci sequence
def fibonacci(n):
    if n <= 1:
        return n
    return fibonacci(n-1) + fibonacci(n-2)

print(f"Fibonacci of 7: {fibonacci(7)}")

# Countdown
def countdown(n):
    if n <= 0:
        print("Done!")
    else:
        print(n)
        countdown(n - 1)

countdown(5)
```

**Output:**
```
Factorial of 5: 120
Fibonacci of 7: 13
5
4
3
2
1
Done!
```

---

## Lambda

Lambda functions are small anonymous functions defined with the `lambda` keyword.

```python
# Simple lambda
square = lambda x: x ** 2
print(f"Square of 5: {square(5)}")

# Lambda with multiple arguments
add = lambda x, y: x + y
print(f"Add 3 and 7: {add(3, 7)}")

# Lambda with map
numbers = [1, 2, 3, 4, 5]
squared = list(map(lambda x: x ** 2, numbers))
print(f"Squared: {squared}")

# Lambda with filter
evens = list(filter(lambda x: x % 2 == 0, numbers))
print(f"Even numbers: {evens}")
```

**Output:**
```
Square of 5: 25
Add 3 and 7: 10
Squared: [1, 4, 9, 16, 25]
Even numbers: [2, 4]
```

---

## Arrays

Arrays (via the array module) store homogeneous data more efficiently than lists.

```python
import array

# Create integer array
int_array = array.array('i', [1, 2, 3, 4, 5])
print(f"Array: {int_array}")

int_array.append(6)
print(f"After append: {int_array}")

int_array.insert(0, 0)
print(f"After insert: {int_array}")

print(f"Element at index 2: {int_array[2]}")
```

**Output:**
```
Array: array('i', [1, 2, 3, 4, 5])
After append: array('i', [1, 2, 3, 4, 5, 6])
After insert: array('i', [0, 1, 2, 3, 4, 5, 6])
Element at index 2: 2
```

---

## Classes/Objects

Classes define blueprints for creating objects with attributes and methods.

### Creating Classes and Objects

```python
class Dog:
    def __init__(self, name, age):
        self.name = name
        self.age = age
    
    def bark(self):
        return f"{self.name} says Woof!"
    
    def get_info(self):
        return f"{self.name} is {self.age} years old"

# Create objects
dog1 = Dog("Buddy", 3)
dog2 = Dog("Max", 5)

print(dog1.get_info())
print(dog1.bark())
print(dog2.get_info())
```

**Output:**
```
Buddy is 3 years old
Buddy says Woof!
Max is 5 years old
```

### The __str__ Method

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age
    
    def __str__(self):
        return f"{self.name} ({self.age})"

person1 = Person("Alice", 30)
print(person1)  # Calls __str__ automatically

# Without __str__, would print object reference
class Car:
    def __init__(self, brand):
        self.brand = brand

car = Car("Toyota")
print(f"With __str__: {person1}")
print(f"Without __str__: {car}")
```

**Output:**
```
Alice (30)
With __str__: Alice (30)
Without __str__: <__main__.Car object at 0x...>
```

### Modify and Delete Properties

```python
class Student:
    def __init__(self, name, grade):
        self.name = name
        self.grade = grade

student = Student("Bob", "A")
print(f"Original: {student.name}, {student.grade}")

# Modify property
student.grade = "A+"
print(f"Modified: {student.name}, {student.grade}")

# Add new property
student.age = 20
print(f"Added age: {student.age}")

# Delete property
del student.age
print("Age deleted")

# Delete object
del student
print("Student object deleted")
```

**Output:**
```
Original: Bob, A
Modified: Bob, A+
Added age: 20
Age deleted
Student object deleted
```

### Class Attributes

```python
class Circle:
    # Class attribute (shared by all instances)
    pi = 3.14159
    
    def __init__(self, radius):
        # Instance attribute (unique to each instance)
        self.radius = radius
    
    def area(self):
        return Circle.pi * self.radius ** 2

circle1 = Circle(5)
circle2 = Circle(3)

print(f"Circle 1 area: {circle1.area():.2f}")
print(f"Circle 2 area: {circle2.area():.2f}")
print(f"Pi is same: {circle1.pi == circle2.pi}")
```

**Output:**
```
Circle 1 area: 78.54
Circle 2 area: 28.27
Pi is same: True
```

---

## Inheritance

Inheritance allows a class to inherit attributes and methods from another class.

```python
class Animal:
    def __init__(self, name):
        self.name = name
    
    def speak(self):
        return "Some sound"

class Cat(Animal):
    def speak(self):
        return f"{self.name} says Meow!"

class Bird(Animal):
    def __init__(self, name, can_fly):
        super().__init__(name)
        self.can_fly = can_fly
    
    def speak(self):
        return f"{self.name} says Tweet!"

cat = Cat("Whiskers")
bird = Bird("Tweety", True)

print(cat.speak())
print(bird.speak())
print(f"Can fly: {bird.can_fly}")
```

**Output:**
```
Whiskers says Meow!
Tweety says Tweet!
Can fly: True
```

---

## Iterators

Iterators are objects that implement `__iter__()` and `__next__()` methods.

```python
# Using built-in iterator
my_list = [1, 2, 3, 4]
my_iter = iter(my_list)

print(next(my_iter))
print(next(my_iter))
print(next(my_iter))

# Custom iterator
class Counter:
    def __init__(self, max_count):
        self.max_count = max_count
        self.current = 0
    
    def __iter__(self):
        return self
    
    def __next__(self):
        if self.current < self.max_count:
            self.current += 1
            return self.current
        raise StopIteration

counter = Counter(3)
for num in counter:
    print(f"Count: {num}")
```

**Output:**
```
1
2
3
Count: 1
Count: 2
Count: 3
```

---

## Polymorphism

Polymorphism allows objects of different classes to be treated through a common interface.

```python
class Shape:
    def area(self):
        pass

class Rectangle(Shape):
    def __init__(self, width, height):
        self.width = width
        self.height = height
    
    def area(self):
        return self.width * self.height

class Circle(Shape):
    def __init__(self, radius):
        self.radius = radius
    
    def area(self):
        return 3.14 * self.radius ** 2

shapes = [Rectangle(4, 5), Circle(3), Rectangle(2, 8)]

for shape in shapes:
    print(f"Area: {shape.area()}")
```

**Output:**
```
Area: 20
Area: 28.26
Area: 16
```

---

## Scope

Scope determines where variables are accessible in your code.

### Local and Global Scope

```python
# Global scope
global_var = "I'm global"

def my_function():
    # Local scope
    local_var = "I'm local"
    print(local_var)
    print(global_var)

my_function()
print(global_var)
# print(local_var)  # Error: not defined in global scope
```

**Output:**
```
I'm local
I'm global
I'm global
```

### Enclosing Scope

```python
def outer_function():
    # Enclosing scope
    outer_var = "I'm in outer"
    
    def inner_function():
        # Local scope
        inner_var = "I'm in inner"
        print(inner_var)
        print(outer_var)
    
    inner_function()
    print(outer_var)

outer_function()
```

**Output:**
```
I'm in inner
I'm in outer
I'm in outer
```

### Global Keyword

```python
counter = 0

def increment():
    global counter
    counter += 1
    print(f"Counter: {counter}")

increment()
increment()
print(f"Global counter: {counter}")

# Without global
def try_modify():
    # This creates a local variable
    value = 10
    value += 5
    print(f"Local value: {value}")

value = 10
try_modify()
print(f"Global value unchanged: {value}")
```

**Output:**
```
Counter: 1
Counter: 2
Global counter: 2
Local value: 15
Global value unchanged: 10
```

### Nonlocal Keyword

```python
def outer():
    count = 0
    
    def inner():
        nonlocal count
        count += 1
        print(f"Inner count: {count}")
    
    inner()
    inner()
    print(f"Outer count: {count}")

outer()

# Without nonlocal
def outer2():
    value = 10
    
    def inner2():
        value = 20  # Creates new local variable
        print(f"Inner value: {value}")
    
    inner2()
    print(f"Outer value unchanged: {value}")

outer2()
```

**Output:**
```
Inner count: 1
Inner count: 2
Outer count: 2
Inner value: 20
Outer value unchanged: 10
```

### LEGB Rule (Local, Enclosing, Global, Built-in)

```python
x = "global"

def outer():
    x = "enclosing"
    
    def inner():
        x = "local"
        print(f"Local x: {x}")
    
    inner()
    print(f"Enclosing x: {x}")

outer()
print(f"Global x: {x}")

# Built-in example
print(f"Built-in len: {len([1, 2, 3])}")
```

**Output:**
```
Local x: local
Enclosing x: enclosing
Global x: global
Built-in len: 3
```

---

## Modules

Modules are Python files containing functions, classes, and variables that can be imported.

### Importing Built-in Modules

```python
# Import entire module
import math
print(f"Pi: {math.pi}")
print(f"Square root of 16: {math.sqrt(16)}")

# Import specific items
from math import pi, sqrt
print(f"Pi: {pi}")
print(f"Sqrt of 25: {sqrt(25)}")

# Import with alias
import math as m
print(f"Ceiling of 4.3: {m.ceil(4.3)}")

# Import all (not recommended)
from random import *
print(f"Random: {randint(1, 10)}")
```

**Output:**
```
Pi: 3.141592653589793
Square root of 16: 4.0
Pi: 3.141592653589793
Sqrt of 25: 5.0
Ceiling of 4.3: 5
Random: 7
```

### Common Built-in Modules

```python
import math
import random
import datetime
import os

print(f"Math floor: {math.floor(4.7)}")
print(f"Random choice: {random.choice(['a', 'b', 'c'])}")
print(f"Current date: {datetime.date.today()}")
print(f"Current directory: {os.getcwd()}")
```

**Output:**
```
Math floor: 4
Random choice: b
Current date: 2026-01-19
Current directory: /workspaces/python-review
```

### Creating Custom Modules

```python
# Example of creating a custom module
# File: mymodule.py
"""
def greet(name):
    return f"Hello, {name}!"

def add(a, b):
    return a + b

person = {
    "name": "Alice",
    "age": 30
}
"""

# Then import and use:
# import mymodule
# print(mymodule.greet("Bob"))
# print(mymodule.add(5, 3))
# print(mymodule.person["name"])

print("Custom modules are Python files you can import")
```

**Output:**
```
Customom modules are Python files you can import
```

### Using dir() Function

```python
import math

# List all names in a module
names = dir(math)
print(f"Number of items in math: {len(names)}")
print(f"First 10 items: {names[:10]}")
print(f"Some functions: pi, sqrt, floor, ceil")
print(f"Has sqrt: {'sqrt' in dir(math)}")

# dir() on built-in types
print(f"\nString methods count: {len([m for m in dir(str) if not m.startswith('_')])}")
```

**Output:**
```
Number of items in math: 65
First 10 items: ['__doc__', '__file__', '__loader__', '__name__', '__package__', '__spec__', 'acos', 'acosh', 'asin', 'asinh']
Some functions: pi, sqrt, floor, ceil
Has sqrt: True

String methods count: 44
```

### Import From Package

```python
# Import specific function
from datetime import datetime, timedelta

now = datetime.now()
tomorrow = now + timedelta(days=1)
print(f"Now: {now.date()}")
print(f"Tomorrow: {tomorrow.date()}")

# Multiple imports
from os import getcwd, listdir
print(f"Current dir: {getcwd()}")
```

**Output:**
```
Now: 2026-01-19
Tomorrow: 2026-01-20
Current dir: /workspaces/python-review
```

---

## Dates

The datetime module provides classes for working with dates and times.

```python
from datetime import datetime, date, timedelta

# Current date and time
now = datetime.now()
print(f"Now: {now}")
print(f"Date: {now.date()}")
print(f"Time: {now.time()}")

# Create specific date
my_date = date(2025, 12, 25)
print(f"Christmas 2025: {my_date}")

# Date arithmetic
tomorrow = now + timedelta(days=1)
print(f"Tomorrow: {tomorrow.date()}")

# Formatting
formatted = now.strftime("%Y-%m-%d %H:%M:%S")
print(f"Formatted: {formatted}")
```

**Output:**
```
Now: 2026-01-19 12:34:56.789123
Date: 2026-01-19
Time: 12:34:56.789123
Christmas 2025: 2025-12-25
Tomorrow: 2026-01-20
Formatted: 2026-01-19 12:34:56
```

---

## Math

The math module provides mathematical functions and constants.

```python
import math

print(f"Absolute value: {math.fabs(-5)}")
print(f"Power: {math.pow(2, 3)}")
print(f"Floor: {math.floor(4.7)}")
print(f"Ceiling: {math.ceil(4.2)}")
print(f"GCD: {math.gcd(48, 18)}")
print(f"Factorial: {math.factorial(5)}")
print(f"Sin(90°): {math.sin(math.radians(90))}")
print(f"Log: {math.log(10)}")
```

**Output:**
```
Absolute value: 5.0
Power: 8.0
Floor: 4
Ceiling: 5
GCD: 6
Factorial: 120
Sin(90°): 1.0
Log: 2.302585092994046
```

---

## JSON

JSON (JavaScript Object Notation) is a lightweight data interchange format.

### Converting Python to JSON

```python
import json

# Python object to JSON
person = {
    "name": "John",
    "age": 30,
    "city": "Boston",
    "hobbies": ["reading", "coding"]
}

json_string = json.dumps(person)
print("Compact JSON:")
print(json_string)
```

**Output:**
```
Compact JSON:
{"name": "John", "age": 30, "city": "Boston", "hobbies": ["reading", "coding"]}
```

### Formatting JSON Output

```python
import json

data = {
    "name": "Alice",
    "age": 25,
    "skills": ["Python", "JavaScript", "SQL"],
    "address": {"city": "NYC", "zip": "10001"}
}

# With indentation
formatted = json.dumps(data, indent=2)
print("Formatted with indent=2:")
print(formatted)

print("\n" + "="*40 + "\n")

# With indentation and sorted keys
sorted_json = json.dumps(data, indent=4, sort_keys=True)
print("Sorted keys with indent=4:")
print(sorted_json)
```

**Output:**
```
Formatted with indent=2:
{
  "name": "Alice",
  "age": 25,
  "skills": [
    "Python",
    "JavaScript",
    "SQL"
  ],
  "address": {
    "city": "NYC",
    "zip": "10001"
  }
}

========================================

Sorted keys with indent=4:
{
    "address": {
        "city": "NYC",
        "zip": "10001"
    },
    "age": 25,
    "name": "Alice",
    "skills": [
        "Python",
        "JavaScript",
        "SQL"
    ]
}
```

### Parsing JSON to Python

```python
import json

# JSON string to Python object
json_data = '{"name": "Jane", "age": 28, "active": true}'
python_obj = json.loads(json_data)

print(f"Parsed object: {python_obj}")
print(f"Type: {type(python_obj)}")
print(f"Name: {python_obj['name']}")
print(f"Active: {python_obj['active']}")
```

**Output:**
```
Parsed object: {'name': 'Jane', 'age': 28, 'active': True}
Type: <class 'dict'>
Name: Jane
Active: True
```

### JSON Data Type Conversion

```python
import json

# Python types to JSON
data = {
    "string": "hello",
    "number": 42,
    "float": 3.14,
    "boolean": True,
    "null": None,
    "list": [1, 2, 3],
    "dict": {"key": "value"}
}

json_str = json.dumps(data)
print("JSON conversion:")
print(json_str)
print(f"\nNote: Python True -> JSON true")
print(f"Note: Python None -> JSON null")
```

**Output:**
```
JSON conversion:
{"string": "hello", "number": 42, "float": 3.14, "boolean": true, "null": null, "list": [1, 2, 3], "dict": {"key": "value"}}

Note: Python True -> JSON true
Note: Python None -> JSON null
```

### Reading/Writing JSON Files

```python
import json

# Write to file
data = {"name": "Bob", "age": 30, "city": "LA"}

with open("data.json", "w") as file:
    json.dump(data, file, indent=2)
print("Data written to file")

# Read from file
with open("data.json", "r") as file:
    loaded_data = json.load(file)

print(f"Loaded data: {loaded_data}")

# Cleanup
import os
os.remove("data.json")
print("File removed")
```

**Output:**
```
Data written to file
Loaded data: {'name': 'Bob', 'age': 30, 'city': 'LA'}
File removed
```

---

## RegEx

Regular expressions (regex) are patterns used for matching strings.

### Basic RegEx Functions

```python
import re

text = "The phone numbers are 123-456-7890 and 987-654-3210"

# findall - returns all matches
pattern = r'\d{3}-\d{3}-\d{4}'
matches = re.findall(pattern, text)
print(f"Phone numbers found: {matches}")

# search - returns first match object
email = "Contact us at info@example.com"
match = re.search(r'[\w\.-]+@[\w\.-]+', email)
if match:
    print(f"Email found: {match.group()}")

# match - checks if pattern matches at start
text = "Hello World"
if re.match(r'Hello', text):
    print("Starts with Hello")
```

**Output:**
```
Phone numbers found: ['123-456-7890', '987-654-3210']
Email found: info@example.com
Starts with Hello
```

### Sub and Split Functions

```python
import re

# sub - replace pattern
text = "Password: 1234"
masked = re.sub(r'\d', 'X', text)
print(f"Masked: {masked}")

# Replace with function
def double_num(match):
    return str(int(match.group()) * 2)

text = "I have 5 apples and 10 oranges"
result = re.sub(r'\d+', double_num, text)
print(f"Doubled: {result}")

# split - split by pattern
words = re.split(r'\s+', "Hello   world  Python")
print(f"Words: {words}")

# Split with limit
text = "a,b,c,d,e"
parts = re.split(r',', text, maxsplit=2)
print(f"Split (max 2): {parts}")
```

**Output:**
```
Masked: Password: XXXX
Doubled: I have 10 apples and 20 oranges
Words: ['Hello', 'world', 'Python']
Split (max 2): ['a', 'b', 'c,d,e']
```

### Metacharacters

```python
import re

# . - any character except newline
print(re.findall(r'h.t', 'hat hit hot hoot'))

# ^ - start of string
print(re.findall(r'^Hello', 'Hello World'))

# $ - end of string
print(re.findall(r'World$', 'Hello World'))

# * - zero or more
print(re.findall(r'ab*c', 'ac abc abbc abbbc'))

# + - one or more
print(re.findall(r'ab+c', 'ac abc abbc'))

# ? - zero or one
print(re.findall(r'colou?r', 'color colour'))

# {n} - exactly n times
print(re.findall(r'\d{3}', '12 123 1234'))

# | - or
print(re.findall(r'cat|dog', 'I have a cat and a dog'))
```

**Output:**
```
['hat', 'hit', 'hot']
['Hello']
['World']
['ac', 'abc', 'abbc', 'abbbc']
['abc', 'abbc']
['color', 'colour']
['123', '123']
['cat', 'dog']
```

### Special Sequences

```python
import re

text = "My number is 555-1234 and email is test@example.com"

# \d - digit [0-9]
print(f"Digits: {re.findall(r'\d', text)}")

# \D - non-digit
print(f"Non-digits (first 10): {re.findall(r'\D', text)[:10]}")

# \w - word character [a-zA-Z0-9_]
print(f"Word chars: {re.findall(r'\w+', text)}")

# \W - non-word character
print(f"Non-word: {re.findall(r'\W', text)}")

# \s - whitespace
print(f"Whitespace count: {len(re.findall(r'\s', text))}")

# \S - non-whitespace
print(f"Non-whitespace (first 5): {re.findall(r'\S+', text)[:5]}")

# \b - word boundary
print(f"Words starting with 'e': {re.findall(r'\be\w+', text)}")
```

**Output:**
```
Digits: ['5', '5', '5', '1', '2', '3', '4']
Non-digits (first 10): ['M', 'y', ' ', 'n', 'u', 'm', 'b', 'e', 'r', ' ']
Word chars: ['My', 'number', 'is', '555', '1234', 'and', 'email', 'is', 'test', 'example', 'com']
Non-word: [' ', ' ', ' ', '-', ' ', ' ', ' ', ' ', '@', '.']
Whitespace count: 8
Non-whitespace (first 5): ['My', 'number', 'is', '555-1234', 'and']
Words starting with 'e': ['email', 'example']
```

### Character Sets

```python
import re

# [abc] - a, b, or c
print(re.findall(r'[aeiou]', 'hello world'))

# [^abc] - not a, b, or c
print(re.findall(r'[^aeiou\s]', 'hello world'))

# [a-z] - range
print(re.findall(r'[A-Z]', 'Hello World'))

# [0-9] - digit range
print(re.findall(r'[0-5]', '0123456789'))

# Multiple ranges
print(re.findall(r'[a-zA-Z0-9]', 'Hello123!'))

# Special characters in sets
text = "Cost: $50, €40, £30"
print(f"Currency symbols: {re.findall(r'[$€£]', text)}")
```

**Output:**
```
['e', 'o', 'o']
['h', 'l', 'l', 'w', 'r', 'l', 'd']
['H', 'W']
['0', '1', '2', '3', '4', '5']
['H', 'e', 'l', 'l', 'o', '1', '2', '3']
Currency symbols: ['$', '€', '£']
```

### Groups and Capturing

```python
import re

# Capturing groups with ()
text = "John: 25, Jane: 30, Bob: 35"
matches = re.findall(r'(\w+): (\d+)', text)
print(f"Name-Age pairs: {matches}")

for name, age in matches:
    print(f"{name} is {age} years old")

# Non-capturing group (?:)
text = "http://example.com https://test.com"
matches = re.findall(r'(?:http|https)://([\w.]+)', text)
print(f"\nDomains: {matches}")

# Named groups
pattern = r'(?P<name>\w+): (?P<age>\d+)'
match = re.search(pattern, "Alice: 28")
if match:
    print(f"\nName: {match.group('name')}, Age: {match.group('age')}")
```

**Output:**
```
Name-Age pairs: [('John', '25'), ('Jane', '30'), ('Bob', '35')]
John is 25 years old
Jane is 30 years old
Bob is 35 years old

Domains: ['example.com', 'test.com']

Name: Alice, Age: 28
```

---

## PIP

PIP is the package installer for Python, used to install and manage third-party packages.

```bash
# Install a package
pip install requests

# Install specific version
pip install requests==2.28.0

# Uninstall package
pip uninstall requests

# List installed packages
pip list

# Show package information
pip show requests

# Install from requirements file
pip install -r requirements.txt

# Freeze current packages
pip freeze > requirements.txt

# Upgrade package
pip install --upgrade requests
```

**Output:**
```
Successfully installed requests-2.28.0
Package uninstalled successfully
Package            Version
------------------ -------
pip                23.0.1
setuptools         65.5.0
requests           2.28.0
```

---

## Try...Except

Exception handling allows you to gracefully handle errors during program execution.

```python
# Basic try-except
try:
    result = 10 / 0
except ZeroDivisionError:
    print("Cannot divide by zero!")

# Multiple exceptions
try:
    num = int("abc")
except ValueError:
    print("Invalid number format!")
except Exception as e:
    print(f"Other error: {e}")

# Try-except-else-finally
try:
    file_data = 100 / 5
except ZeroDivisionError:
    print("Error occurred")
else:
    print(f"Result: {file_data}")
finally:
    print("Cleanup complete")

# Raising exceptions
def check_age(age):
    if age < 0:
        raise ValueError("Age cannot be negative")
    return age

try:
    check_age(-5)
except ValueError as e:
    print(f"Error: {e}")
```

**Output:**
```
Cannot divide by zero!
Invalid number format!
Result: 20.0
Cleanup complete
Error: Age cannot be negative
```

---

## User Input

The `input()` function reads user input from the console as a string.

```python
# Basic input
name = input("Enter your name: ")
print(f"Hello, {name}!")

# Converting input
age = int(input("Enter your age: "))
print(f"You are {age} years old")

# Multiple inputs
x, y = input("Enter two numbers separated by space: ").split()
x, y = int(x), int(y)
print(f"Sum: {x + y}")

# Input validation
while True:
    try:
        num = int(input("Enter a positive number: "))
        if num > 0:
            print(f"You entered: {num}")
            break
        else:
            print("Please enter a positive number")
    except ValueError:
        print("Invalid input! Enter a number")
```

**Example Interaction:**
```
Enter your name: Alice
Hello, Alice!
Enter your age: 25
You are 25 years old
Enter two numbers separated by space: 10 20
Sum: 30
```

---

## String Formatting

Python offers multiple ways to format strings for output.

```python
name = "Alice"
age = 30
price = 19.99

# f-strings (Python 3.6+)
print(f"Name: {name}, Age: {age}")
print(f"Price: ${price:.2f}")

# format() method
print("Name: {}, Age: {}".format(name, age))
print("Name: {0}, Age: {1}, Again: {0}".format(name, age))

# % formatting (older style)
print("Name: %s, Age: %d" % (name, age))
print("Price: $%.2f" % price)

# Advanced formatting
number = 1234567.89
print(f"Comma separator: {number:,.2f}")
print(f"Percentage: {0.85:.1%}")
print(f"Right aligned: {name:>10}")
print(f"Left aligned: {name:<10}")
```

**Output:**
```
Name: Alice, Age: 30
Price: $19.99
Name: Alice, Age: 30
Name: Alice, Age: 30, Again: Alice
Name: Alice, Age: 30
Price: $19.99
Comma separator: 1,234,567.89
Percentage: 85.0%
Right aligned:      Alice
Left aligned: Alice     
```

---

## File Handling

Python provides built-in functions for reading from and writing to files.

```python
# Writing to a file
with open('sample.txt', 'w') as file:
    file.write("Hello, World!\n")
    file.write("Python file handling\n")
print("File written successfully")

# Reading from a file
with open('sample.txt', 'r') as file:
    content = file.read()
    print("File content:")
    print(content)

# Reading line by line
with open('sample.txt', 'r') as file:
    for line in file:
        print(f"Line: {line.strip()}")

# Appending to a file
with open('sample.txt', 'a') as file:
    file.write("Appended line\n")
print("Line appended")

# Reading lines into list
with open('sample.txt', 'r') as file:
    lines = file.readlines()
    print(f"Total lines: {len(lines)}")

# File operations
import os
if os.path.exists('sample.txt'):
    print("File exists")
    os.remove('sample.txt')
    print("File deleted")
```

**Output:**
```
File written successfully
File content:
Hello, World!
Python file handling

Line: Hello, World!
Line: Python file handling
Line appended
Total lines: 3
File exists
File deleted
```

---

## Virtual Environment

Virtual environments create isolated Python environments for different projects, managing dependencies separately.

```bash
# Create virtual environment
python -m venv myenv

# Activate virtual environment
# On Linux/Mac:
source myenv/bin/activate
# On Windows:
myenv\Scripts\activate

# Install packages in virtual environment
pip install requests numpy

# Deactivate virtual environment
deactivate

# Create with specific Python version
python3.9 -m venv myenv39

# Using venv with requirements
python -m venv project_env
source project_env/bin/activate
pip install -r requirements.txt

# Remove virtual environment
rm -rf myenv
```

**Output:**
```
Created virtual environment at: myenv
(myenv) $ pip list
Package    Version
---------- -------
pip        23.0.1
setuptools 65.5.0

(myenv) $ pip install requests
Successfully installed requests-2.28.0

Deactivated virtual environment
```

---

## Summary

This guide covered essential Python topics from basic syntax to virtual environments. Key takeaways:

- **Basics**: Python uses indentation, dynamic typing, and has rich built-in data types
- **Control Flow**: if/else, while, for loops control program execution
- **Functions**: Reusable code blocks, including lambda functions
- **OOP**: Classes, inheritance, and polymorphism for structured programming
- **Modules**: Import and use built-in or third-party libraries
- **File I/O**: Read and write files with context managers
- **Error Handling**: Try/except blocks for robust code
- **Environment**: Virtual environments isolate project dependencies

Practice these concepts to build a strong Python foundation!
