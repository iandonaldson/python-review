# Python Basics Guide

A comprehensive guide covering fundamental Python concepts with examples and outputs.

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

```python
name = "Alice"
age = 30
height = 5.6
is_student = False

print(f"Name: {name}, Age: {age}, Height: {height}, Student: {is_student}")
```

**Output:**
```
Name: Alice, Age: 30, Height: 5.6, Student: False
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

```python
x = 10
y = 3.5
z = 2 + 4j

print(f"Integer: {x}")
print(f"Float: {y}")
print(f"Complex: {z}")
print(f"Addition: {x + y}")
print(f"Power: {x ** 2}")
```

**Output:**
```
Integer: 10
Float: 3.5
Complex: (2+4j)
Addition: 13.5
Power: 100
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

```python
text = "Python Programming"

print(f"Original: {text}")
print(f"Uppercase: {text.upper()}")
print(f"Lowercase: {text.lower()}")
print(f"First 6 chars: {text[:6]}")
print(f"Replace: {text.replace('Python', 'Java')}")
print(f"Split: {text.split()}")
```

**Output:**
```
Original: Python Programming
Uppercase: PYTHON PROGRAMMING
Lowercase: python programming
First 6 chars: Python
Replace: Java Programming
Split: ['Python', 'Programming']
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

Python supports arithmetic, comparison, logical, and assignment operators.

```python
# Arithmetic
x = 10
y = 3
print(f"Addition: {x + y}")
print(f"Division: {x / y}")
print(f"Floor division: {x // y}")
print(f"Modulus: {x % y}")

# Comparison
print(f"Equal: {x == y}")
print(f"Not equal: {x != y}")

# Logical
print(f"And: {True and False}")
print(f"Or: {True or False}")
```

**Output:**
```
Addition: 13
Division: 3.3333333333333335
Floor division: 3
Modulus: 1
Equal: False
Not equal: True
And: False
Or: True
```

---

## Lists

Lists are ordered, mutable collections that can contain mixed data types.

```python
fruits = ["apple", "banana", "cherry"]
numbers = [1, 2, 3, 4, 5]

print(f"Fruits: {fruits}")
print(f"First fruit: {fruits[0]}")
fruits.append("orange")
print(f"After append: {fruits}")
fruits.remove("banana")
print(f"After remove: {fruits}")
print(f"List length: {len(fruits)}")
```

**Output:**
```
Fruits: ['apple', 'banana', 'cherry']
First fruit: apple
After append: ['apple', 'banana', 'cherry', 'orange']
After remove: ['apple', 'cherry', 'orange']
List length: 3
```

---

## Tuples

Tuples are ordered, immutable collections defined with parentheses.

```python
coordinates = (10, 20, 30)
single_item = (42,)

print(f"Tuple: {coordinates}")
print(f"First element: {coordinates[0]}")
print(f"Slice: {coordinates[1:]}")
print(f"Count of 20: {coordinates.count(20)}")
print(f"Index of 30: {coordinates.index(30)}")
```

**Output:**
```
Tuple: (10, 20, 30)
First element: 10
Slice: (20, 30)
Count of 20: 1
Index of 30: 2
```

---

## Sets

Sets are unordered collections of unique elements, useful for mathematical operations.

```python
set1 = {1, 2, 3, 4}
set2 = {3, 4, 5, 6}

print(f"Set 1: {set1}")
print(f"Set 2: {set2}")
print(f"Union: {set1 | set2}")
print(f"Intersection: {set1 & set2}")
print(f"Difference: {set1 - set2}")

set1.add(7)
print(f"After adding 7: {set1}")
```

**Output:**
```
Set 1: {1, 2, 3, 4}
Set 2: {3, 4, 5, 6}
Union: {1, 2, 3, 4, 5, 6}
Intersection: {3, 4}
Difference: {1, 2}
After adding 7: {1, 2, 3, 4, 7}
```

---

## Dictionaries

Dictionaries store key-value pairs, providing fast lookup by key.

```python
person = {
    "name": "Bob",
    "age": 25,
    "city": "New York"
}

print(f"Person: {person}")
print(f"Name: {person['name']}")
print(f"Age: {person.get('age')}")

person["job"] = "Engineer"
print(f"After adding job: {person}")
print(f"Keys: {list(person.keys())}")
print(f"Values: {list(person.values())}")
```

**Output:**
```
Person: {'name': 'Bob', 'age': 25, 'city': 'New York'}
Name: Bob
Age: 25
After adding job: {'name': 'Bob', 'age': 25, 'city': 'New York', 'job': 'Engineer'}
Keys: ['name', 'age', 'city', 'job']
Values: ['Bob', 25, 'New York', 'Engineer']
```

---

## If...Else

Conditional statements control program flow based on boolean expressions.

```python
temperature = 25

if temperature > 30:
    print("It's hot!")
elif temperature > 20:
    print("It's pleasant")
else:
    print("It's cold!")

# Ternary operator
status = "Adult" if age >= 18 else "Minor"
print(f"Status: {status}")
```

**Output:**
```
It's pleasant
Status: Adult
```

---

## While Loops

While loops repeat code as long as a condition remains true.

```python
count = 0

while count < 5:
    print(f"Count is: {count}")
    count += 1

# While with break
num = 0
while True:
    if num == 3:
        break
    print(f"Num: {num}")
    num += 1
```

**Output:**
```
Count is: 0
Count is: 1
Count is: 2
Count is: 3
Count is: 4
Num: 0
Num: 1
Num: 2
```

---

## For Loops

For loops iterate over sequences like lists, strings, or ranges.

```python
# Loop through list
colors = ["red", "green", "blue"]
for color in colors:
    print(f"Color: {color}")

# Loop through range
for i in range(3):
    print(f"Number: {i}")

# Loop with enumerate
for idx, color in enumerate(colors):
    print(f"{idx}: {color}")
```

**Output:**
```
Color: red
Color: green
Color: blue
Number: 0
Number: 1
Number: 2
0: red
1: green
2: blue
```

---

## Functions

Functions are reusable blocks of code defined with the `def` keyword.

```python
def greet(name):
    return f"Hello, {name}!"

def add_numbers(a, b=10):
    return a + b

print(greet("Alice"))
print(f"Sum: {add_numbers(5)}")
print(f"Sum with both args: {add_numbers(5, 15)}")

# Multiple return values
def get_stats(numbers):
    return min(numbers), max(numbers), sum(numbers)

min_val, max_val, total = get_stats([1, 2, 3, 4, 5])
print(f"Min: {min_val}, Max: {max_val}, Total: {total}")
```

**Output:**
```
Hello, Alice!
Sum: 15
Sum with both args: 20
Min: 1, Max: 5, Total: 15
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

```python
# Global scope
global_var = "I'm global"

def outer_function():
    # Enclosing scope
    outer_var = "I'm in outer"
    
    def inner_function():
        # Local scope
        inner_var = "I'm in inner"
        print(inner_var)
        print(outer_var)
        print(global_var)
    
    inner_function()

outer_function()

# Global keyword
counter = 0

def increment():
    global counter
    counter += 1
    print(f"Counter: {counter}")

increment()
increment()
```

**Output:**
```
I'm in inner
I'm in outer
I'm global
Counter: 1
Counter: 2
```

---

## Modules

Modules are Python files containing functions, classes, and variables that can be imported.

```python
# Built-in modules
import math
import random
from datetime import datetime

print(f"Pi: {math.pi}")
print(f"Square root of 16: {math.sqrt(16)}")
print(f"Random number: {random.randint(1, 10)}")
print(f"Current time: {datetime.now()}")

# Import with alias
import math as m
print(f"Ceiling of 4.3: {m.ceil(4.3)}")
```

**Output:**
```
Pi: 3.141592653589793
Square root of 16: 4.0
Random number: 7
Current time: 2026-01-19 12:34:56.789123
Ceiling of 4.3: 5
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

```python
import json

# Python object to JSON
person = {
    "name": "John",
    "age": 30,
    "city": "Boston",
    "hobbies": ["reading", "coding"]
}

json_string = json.dumps(person, indent=2)
print("JSON string:")
print(json_string)

# JSON to Python object
json_data = '{"name": "Jane", "age": 28, "active": true}'
python_obj = json.loads(json_data)
print(f"\nParsed object: {python_obj}")
print(f"Name: {python_obj['name']}")
```

**Output:**
```
JSON string:
{
  "name": "John",
  "age": 30,
  "city": "Boston",
  "hobbies": [
    "reading",
    "coding"
  ]
}

Parsed object: {'name': 'Jane', 'age': 28, 'active': True}
Name: Jane
```

---

## RegEx

Regular expressions (regex) are patterns used for matching strings.

```python
import re

text = "The phone numbers are 123-456-7890 and 987-654-3210"

# Find all matches
pattern = r'\d{3}-\d{3}-\d{4}'
matches = re.findall(pattern, text)
print(f"Phone numbers found: {matches}")

# Search for pattern
email = "Contact us at info@example.com"
if re.search(r'[\w\.-]+@[\w\.-]+', email):
    print("Email found!")

# Replace pattern
new_text = re.sub(r'\d', 'X', "Password: 1234")
print(f"Masked: {new_text}")

# Split by pattern
words = re.split(r'\s+', "Hello   world  Python")
print(f"Words: {words}")
```

**Output:**
```
Phone numbers found: ['123-456-7890', '987-654-3210']
Email found!
Masked: Password: XXXX
Words: ['Hello', 'world', 'Python']
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
