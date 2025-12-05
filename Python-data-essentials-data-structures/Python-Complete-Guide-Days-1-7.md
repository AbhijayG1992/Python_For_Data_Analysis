# 🐍 Python Complete Learning Guide (Days 1-7)

## 📅 Complete Course Schedule

### Days 1-7: Python Fundamentals & Data Science

| Day | Topics | Key Concepts |
|-----|--------|--------------|
| **Day 1** | Python Basics, Variables, Data Types, Operators, Control Flow (if-else) | Keywords, Identifiers, Comments, Indentation, Input/Output |
| **Day 2** | Loops (while, for), break & continue, Lists | Control flow, Iteration, List operations |
| **Day 3** | Tuples, Sets, Dictionaries, Strings | Data structures, String manipulation |
| **Day 4** | Advanced Data Structures, Nested Structures | Complex data organization |
| **Day 5** | Functions - Introduction, Types, Arguments, Recursion | Function definition, scope, parameters |
| **Day 6** | Lambda Functions, Modules, Packages, File Handling | Advanced functions, imports, I/O operations |
| **Day 7** | Exception Handling, Debugging, OOP Basics | Error handling, Classes, Objects |

---

## Day 1: Python Fundamentals

### Keywords and Identifiers

**Keywords** are reserved words in Python with special meanings.

```python
import keyword
print(keyword.kwlist)  # View all keywords
print(keyword.iskeyword('for'))  # True
```

**Identifiers** are names for variables, functions, classes, etc.

**Rules:**
- Must start with letter (a-z, A-Z) or underscore (_)
- Can contain letters, digits, underscores
- Cannot be a Python keyword
- Case-sensitive

```python
# Valid identifiers
user_name = "Alice"
_age = 25
MAX_SIZE = 100

# Naming conventions (PEP 8)
# Variables/functions: lowercase_with_underscores
# Classes: PascalCase
# Constants: UPPERCASE_WITH_UNDERSCORES
```

### Comments and Indentation

```python
# Single-line comment

"""
Multi-line comment
using triple quotes
"""

# Indentation (4 spaces recommended)
if 5 > 2:
    print("Five is greater")  # Indented block
    print("This is also in the block")
```

### Variables and Data Types

```python
# Integer
age = 25
print(type(age))  # <class 'int'>

# Float
price = 19.99
print(type(price))  # <class 'float'>

# String
name = "Python"
print(type(name))  # <class 'str'>

# Boolean
is_active = True
print(type(is_active))  # <class 'bool'>
```

### Operators

```python
# Arithmetic Operators
x = 10
y = 3
print(x + y)   # 13 - Addition
print(x - y)   # 7 - Subtraction
print(x * y)   # 30 - Multiplication
print(x / y)   # 3.333... - Division
print(x // y)  # 3 - Integer Division
print(x % y)   # 1 - Modulus
print(x ** y)  # 1000 - Exponentiation

# Comparison Operators
print(x == y)  # False
print(x != y)  # True
print(x > y)   # True
print(x < y)   # False
print(x >= y)  # True
print(x <= y)  # False

# Logical Operators
a = True
b = False
print(a and b)  # False
print(a or b)   # True
print(not a)    # False
```

### Input and Output

```python
# Output
print("Hello, World!")
print("Name:", name, "Age:", age)
print(f"My name is {name} and I'm {age} years old")  # f-string

# Input (always returns string)
user_input = input("Enter your name: ")
age_input = int(input("Enter your age: "))  # Convert to int
```

### Control Flow: if-else

```python
temperature = 25

if temperature > 30:
    print("It's hot!")
elif temperature > 20:
    print("It's pleasant!")
else:
    print("It's cold!")

# Logical operators in conditions
score = 85
if score >= 80 and score < 90:
    print("Grade: B")
```

---

## Day 2: Loops and Lists

### While Loop

```python
count = 0
while count < 5:
    print(f"Count: {count}")
    count += 1

# While with user input
password = ""
while password != "secret":
    password = input("Enter password: ")
print("Access granted!")
```

### For Loop

```python
# Iterate over a list
fruits = ['apple', 'banana', 'cherry']
for fruit in fruits:
    print(f"I like {fruit}")

# Iterate over a range
for i in range(5):
    print(i)  # 0, 1, 2, 3, 4

# Range with start and stop
for i in range(2, 8):
    print(i)  # 2, 3, 4, 5, 6, 7

# Range with step
for i in range(0, 10, 2):
    print(i)  # 0, 2, 4, 6, 8
```

### Break and Continue

```python
# Break - exit loop
for i in range(10):
    if i == 5:
        break
    print(i)  # 0, 1, 2, 3, 4

# Continue - skip to next iteration
for i in range(5):
    if i == 2:
        continue
    print(i)  # 0, 1, 3, 4
```

### Lists

```python
# Creating lists
numbers = [1, 2, 3, 4, 5]
mixed = [1, "hello", 3.14, True]

# Accessing elements (0-indexed)
print(numbers[0])   # 1
print(numbers[-1])  # 5 (last element)

# List methods
numbers.append(6)        # Add to end
numbers.insert(0, 0)     # Insert at index
numbers.remove(3)        # Remove by value
popped = numbers.pop()   # Remove and return last
numbers.extend([7, 8])   # Add multiple items

# List operations
print(len(numbers))      # Length
print(3 in numbers)      # Check membership
print(numbers[1:4])      # Slicing

# List comprehension
squares = [x**2 for x in range(5)]  # [0, 1, 4, 9, 16]
evens = [x for x in range(10) if x % 2 == 0]  # [0, 2, 4, 6, 8]
```

---

## Day 3: Tuples, Sets, Dictionaries, Strings

### Tuples

```python
# Immutable sequences
coordinates = (10, 20)
rgb = (255, 128, 0)

# Accessing elements
print(coordinates[0])  # 10

# Tuple unpacking
x, y = coordinates
print(f"x={x}, y={y}")

# Tuples are immutable
# coordinates[0] = 15  # Error!
```

### Sets

```python
# Unordered collection of unique elements
fruits = {'apple', 'banana', 'cherry'}
numbers = {1, 2, 3, 3, 4}  # Duplicates removed: {1, 2, 3, 4}

# Set operations
fruits.add('orange')
fruits.remove('banana')
print('apple' in fruits)  # True

# Set operations
set1 = {1, 2, 3}
set2 = {3, 4, 5}
print(set1 | set2)  # Union: {1, 2, 3, 4, 5}
print(set1 & set2)  # Intersection: {3}
print(set1 - set2)  # Difference: {1, 2}
```

### Dictionaries

```python
# Key-value pairs
student = {
    'name': 'Alice',
    'age': 20,
    'grade': 'A'
}

# Accessing values
print(student['name'])        # Alice
print(student.get('age'))     # 20
print(student.get('email', 'N/A'))  # N/A (default)

# Modifying dictionaries
student['age'] = 21           # Update
student['email'] = 'alice@example.com'  # Add
del student['grade']          # Delete

# Dictionary methods
print(student.keys())         # dict_keys(['name', 'age', 'email'])
print(student.values())       # dict_values(['Alice', 21, 'alice@...'])
print(student.items())        # Key-value pairs

# Iterating
for key, value in student.items():
    print(f"{key}: {value}")
```

### Strings

```python
# String creation
text = "Hello, Python!"
multiline = """This is
a multiline
string"""

# String methods
print(text.upper())           # HELLO, PYTHON!
print(text.lower())           # hello, python!
print(text.strip())           # Remove whitespace
print(text.replace('Hello', 'Hi'))  # Hi, Python!
print(text.split(','))        # ['Hello', ' Python!']

# String formatting
name = "Alice"
age = 25
print(f"Name: {name}, Age: {age}")  # f-string
print("Name: {}, Age: {}".format(name, age))  # format()
print("Name: %s, Age: %d" % (name, age))  # % formatting

# String operations
print(len(text))              # Length
print(text[0])                # First character
print(text[7:13])             # Slicing: Python
print('Python' in text)       # True
```

---

## Day 4: Advanced Data Structures

### Nested Data Structures

```python
# List of dictionaries
students = [
    {'name': 'Alice', 'age': 20, 'grade': 'A'},
    {'name': 'Bob', 'age': 22, 'grade': 'B'},
    {'name': 'Charlie', 'age': 21, 'grade': 'A'}
]

# Accessing nested data
print(students[0]['name'])  # Alice

# Iterating nested structures
for student in students:
    print(f"{student['name']}: {student['grade']}")

# Dictionary with lists
courses = {
    'Math': [90, 85, 88],
    'Science': [92, 89, 91],
    'English': [88, 90, 87]
}

print(courses['Math'][0])  # 90

# Nested dictionaries
company = {
    'IT': {
        'employees': 50,
        'manager': 'John'
    },
    'HR': {
        'employees': 10,
        'manager': 'Jane'
    }
}

print(company['IT']['manager'])  # John
```

---

## Day 5: Functions

### Introduction to Functions

```python
# Function definition
def greet(name):
    """This function greets a person"""
    print(f"Hello, {name}!")

# Function call
greet("Alice")  # Hello, Alice!

# Function with return value
def add(a, b):
    return a + b

result = add(5, 3)
print(result)  # 8
```

### Types of Functions

```python
# Built-in functions
print(len([1, 2, 3]))  # 3
print(max(1, 5, 3))    # 5
print(abs(-10))        # 10

# User-defined functions
def calculate_area(length, width):
    return length * width

# Functions without return (returns None)
def display_info(name, age):
    print(f"Name: {name}")
    print(f"Age: {age}")
```

### Function Arguments

```python
# Positional arguments
def power(base, exponent):
    return base ** exponent

print(power(2, 3))  # 8

# Keyword arguments
print(power(exponent=3, base=2))  # 8

# Default arguments
def greet(name, greeting="Hello"):
    return f"{greeting}, {name}!"

print(greet("Alice"))              # Hello, Alice!
print(greet("Bob", "Hi"))          # Hi, Bob!

# Variable-length arguments (*args)
def sum_all(*numbers):
    return sum(numbers)

print(sum_all(1, 2, 3, 4, 5))  # 15

# Keyword variable-length arguments (**kwargs)
def print_info(**info):
    for key, value in info.items():
        print(f"{key}: {value}")

print_info(name="Alice", age=25, city="NYC")
```

### Recursive Functions

```python
# Factorial using recursion
def factorial(n):
    if n == 0 or n == 1:
        return 1
    return n * factorial(n - 1)

print(factorial(5))  # 120

# Fibonacci sequence
def fibonacci(n):
    if n <= 1:
        return n
    return fibonacci(n-1) + fibonacci(n-2)

print(fibonacci(6))  # 8
```

### Variable Scope

```python
# Global scope
global_var = "I'm global"

def my_function():
    # Local scope
    local_var = "I'm local"
    print(global_var)  # Can access global
    print(local_var)

my_function()
# print(local_var)  # Error! Not accessible outside function

# Modifying global variable
count = 0

def increment():
    global count
    count += 1

increment()
print(count)  # 1
```

---

## Day 6: Lambda, Modules, File Handling

### Lambda Functions

```python
# Lambda syntax: lambda arguments: expression
square = lambda x: x ** 2
print(square(5))  # 25

add = lambda a, b: a + b
print(add(3, 4))  # 7

# Lambda with map()
numbers = [1, 2, 3, 4, 5]
squared = list(map(lambda x: x**2, numbers))
print(squared)  # [1, 4, 9, 16, 25]

# Lambda with filter()
evens = list(filter(lambda x: x % 2 == 0, numbers))
print(evens)  # [2, 4]

# Lambda with sorted()
students = [
    {'name': 'Alice', 'grade': 85},
    {'name': 'Bob', 'grade': 92},
    {'name': 'Charlie', 'grade': 78}
]
sorted_students = sorted(students, key=lambda x: x['grade'], reverse=True)
```

### Modules and Packages

```python
# Importing modules
import math
print(math.pi)        # 3.14159...
print(math.sqrt(16))  # 4.0

# Import specific functions
from math import sqrt, pow
print(sqrt(25))  # 5.0

# Import with alias
import datetime as dt
print(dt.datetime.now())

# Common modules
import random
print(random.randint(1, 10))  # Random integer
print(random.choice(['a', 'b', 'c']))  # Random choice

import os
print(os.getcwd())  # Current directory
```

### File Handling

```python
# Writing to a file
with open('example.txt', 'w') as file:
    file.write("Hello, World!\n")
    file.write("This is a test file.")

# Reading from a file
with open('example.txt', 'r') as file:
    content = file.read()
    print(content)

# Reading line by line
with open('example.txt', 'r') as file:
    for line in file:
        print(line.strip())

# Appending to a file
with open('example.txt', 'a') as file:
    file.write("\nAppended line")

# File modes:
# 'r' - Read (default)
# 'w' - Write (overwrites)
# 'a' - Append
# 'r+' - Read and write
# 'b' - Binary mode
```

---

## Day 7: Exception Handling, Debugging, OOP

### Exception Handling

```python
# Basic try-except
try:
    number = int(input("Enter a number: "))
    result = 100 / number
    print(f"Result: {result}")
except ValueError:
    print("Invalid input! Please enter a number.")
except ZeroDivisionError:
    print("Cannot divide by zero!")
except Exception as e:
    print(f"An error occurred: {e}")
finally:
    print("Execution completed.")

# Raising exceptions
def validate_age(age):
    if age < 0:
        raise ValueError("Age cannot be negative")
    return age

# Custom exceptions
class InvalidEmailError(Exception):
    pass

def validate_email(email):
    if '@' not in email:
        raise InvalidEmailError("Email must contain @")
```

### Debugging Python

```python
# Using print statements
def calculate_average(numbers):
    print(f"Debug: numbers = {numbers}")  # Debug print
    total = sum(numbers)
    print(f"Debug: total = {total}")
    return total / len(numbers)

# Using assert
def divide(a, b):
    assert b != 0, "Divisor cannot be zero"
    return a / b

# Python debugger (pdb)
import pdb

def buggy_function(x):
    pdb.set_trace()  # Breakpoint
    result = x * 2
    return result
```

### Object-Oriented Programming Basics

```python
# Class definition
class Dog:
    # Class attribute
    species = "Canis familiaris"
    
    # Constructor
    def __init__(self, name, age):
        # Instance attributes
        self.name = name
        self.age = age
    
    # Instance method
    def bark(self):
        return f"{self.name} says Woof!"
    
    # Method with parameters
    def birthday(self):
        self.age += 1
        return f"{self.name} is now {self.age} years old"

# Creating objects
dog1 = Dog("Buddy", 3)
dog2 = Dog("Max", 5)

print(dog1.bark())      # Buddy says Woof!
print(dog1.birthday())  # Buddy is now 4 years old

# Inheritance
class GoldenRetriever(Dog):
    def __init__(self, name, age, color):
        super().__init__(name, age)
        self.color = color
    
    # Method overriding
    def bark(self):
        return f"{self.name} says Woof Woof! (Golden Retriever)"

golden = GoldenRetriever("Charlie", 2, "Golden")
print(golden.bark())
```

---

## 🎯 Practice Projects

### Project 1: Tax Calculator
```python
amount = float(input("Enter amount: "))
tax_rate = float(input("Enter tax rate (e.g., 0.06): "))
total = amount + (amount * tax_rate)
print(f"Total with tax: ${total:.2f}")
```

### Project 2: Age Calculator
```python
age = int(input("How old are you? "))
decades = age // 10
years = age % 10
print(f"You are {decades} decades and {years} years old.")
```

### Project 3: Rock, Paper, Scissors
```python
import random

choices = ["rock", "paper", "scissors"]
computer = random.choice(choices)
user = input("Choose rock, paper, or scissors: ").lower()

print(f"Computer chose: {computer}")

if computer == user:
    print("TIE!")
elif (user == "rock" and computer == "scissors") or \
     (user == "paper" and computer == "rock") or \
     (user == "scissors" and computer == "paper"):
    print("YOU WIN!")
else:
    print("YOU LOSE!")
```

### Project 4: Loan Calculator
```python
money_owed = float(input("Loan amount: "))
apr = float(input("Annual percentage rate: "))
payment = float(input("Monthly payment: "))
months = int(input("Number of months: "))

monthly_rate = apr / 100 / 12

for i in range(months):
    interest = money_owed * monthly_rate
    money_owed += interest
    
    if money_owed - payment < 0:
        print(f"Final payment: ${money_owed:.2f}")
        print(f"Paid off in {i+1} months")
        break
    
    money_owed -= payment
    print(f"Month {i+1}: Paid ${payment:.2f}, Interest ${interest:.2f}, Remaining ${money_owed:.2f}")
```

---

## 📚 Key Takeaways

### Days 1-2: Foundations
- Python syntax, data types, operators
- Control flow (if-else, loops)
- Lists and basic data structures

### Days 3-4: Data Structures
- Tuples, sets, dictionaries, strings
- Nested data structures
- Data manipulation techniques

### Days 5-6: Functions & Modules
- Function definition and arguments
- Lambda functions
- Modules, packages, file handling

### Day 7: Advanced Concepts
- Exception handling
- Debugging techniques
- Object-oriented programming basics

---

## 🚀 Next Steps

After completing Days 1-7, proceed to:
- **Days 8-12**: SQL for Data Analysis
- **Advanced Topics**: Regular Expressions, Web APIs, Data Analysis Libraries

**Happy Learning! 🎉**
