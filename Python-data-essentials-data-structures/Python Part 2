Here are detailed notes formatted for a `README.md` file, based on the provided course transcript.

````markdown
# Python 3 Fundamentals - Course Notes

This document contains detailed notes from the "Python 3 Fundamentals" course by Sarah Holderness on Pluralsight. The notes are organized by module and cover all major topics, concepts, and code examples discussed.

## Course Overview

An introductory course to the Python 3 programming language, designed for beginners with no prior programming experience. The course focuses on teaching the fundamentals through hands-on, practical projects.

### Key Topics Covered:
* **Core Concepts:** Writing a Python program, variables, data types, and operators.
* **Program Flow:** Conditionals (`if`/`elif`/`else`), loops (`for`), and functions.
* **Data Structures:** Lists and Dictionaries.
* **Interactivity:** Handling user input and producing output.
* **External Data:** Making web requests to APIs and parsing JSON data.
* **Package Management:** Installing and using Python packages with `pip` and virtual environments.
* **Object-Oriented Programming:** Classes, objects, and inheritance.
* **File Handling:** Reading from, writing to, and manipulating files and directories.
* **Error Handling:** Using `try`/`except` blocks to handle exceptions.

### Projects Built:
* Loan Calculator
* Rock, Paper, Scissors Game
* Acronym Translator
* Weather Reader
* Expense Summer
* Company Payroll System
* File Organizer

---

## 1. Getting Started: Data Types & Installation

### 1.1. Why Python?
* **Versatile:** Can be used for web development, data science, machine learning, and more.
* **Strong Community:** A vast collection of libraries for almost any task.
* **Easy to Learn:** Syntax is readable and concise, similar to English.

### 1.2. Running Python Code
There are two primary ways to run Python code:
1.  **Interactive Shell:** Accessed by typing `python` or `python3` in the terminal. It's great for testing small snippets of code one line at a time. The prompt is indicated by `>>>`.
2.  **Python Script:** A text file with a `.py` extension (e.g., `hello.py`). Used for writing longer, reusable programs.

### 1.3. Variables and Basic Data Types
Python is dynamically typed, meaning it infers the data type of a variable at runtime.

* **Variable:** A named location in memory that stores a value.
    ```python
    length = 10
    width = 20
    ```
* **Integer (`int`):** A whole number (e.g., `10`, `-5`, `200`).
* **Float (`float`):** A number with a decimal point (e.g., `10.5`, `0.06`).

### 1.4. Arithmetic Operators
* Addition: `+`
* Subtraction: `-`
* Multiplication: `*`
* Division: `/`

### 1.5. Installation and Setup
#### Installing Python
1.  Check if Python 3 is installed: `python3 --version` (macOS/Linux) or `python --version` (Windows).
2.  If not, download it from [python.org/downloads](https://python.org/downloads).
3.  During installation on Windows, **check the box "Add python.exe to PATH"**.

#### Installing Visual Studio Code (VS Code)
1.  Download from [code.visualstudio.com](https://code.visualstudio.com).
2.  Install the **Python extension** by Microsoft from the Extensions view.
3.  Select the Python interpreter:
    * Open the Command Palette (`View > Command Palette` or `Ctrl+Shift+P`).
    * Type `Python: Select Interpreter`.
    * Choose your installed Python 3 version.

### Project: Tax Calculator
This program calculates the total cost of an item including sales tax.

```python
# tax.py

# Hard-coded values for amount and tax rate
amount = 100
tax = 0.06

# Calculation
total = amount + amount * tax

# Print the result to the console
print(total) # Output: 106.0
````

-----

## 2\. Strings, Input/Output, and More Data Types

### 2.1. Strings (`str`)

  * Used for text.
  * Created by enclosing text in single (`'`) or double (`"`) quotes.
  * Use double quotes if the string contains a single quote (apostrophe), and vice versa.
    ```python
    name = "Sarah"
    store_name = "Sarah's Store"
    ```
  * **String Concatenation:** Joining strings using the `+` operator.
    ```python
    greeting = "Hello" + " " + "Sarah" # "Hello Sarah"
    ```
  * **Special Characters:** `\n` creates a new line.

### 2.2. Input and Output

  * **`print()`:** A built-in function to display output to the console.
  * **`input()`:** A built-in function to prompt the user for input. It always returns the input as a string.
    ```python
    name = input("What's your name?\n")
    print("Hello " + name)
    ```

### 2.3. Type Conversion

Functions to convert values from one type to another.

  * `int()`: Converts to an integer.
  * `float()`: Converts to a float.
  * `str()`: Converts to a string.

<!-- end list -->

```python
# input() returns a string, so we must convert it to a number for calculations
age_string = input("How old are you? ")
age_int = int(age_string)
```

### Project: Age Calculator

Calculates a person's age in decades and years.

```python
# decades.py

age_str = input("How old are you? ")
age = int(age_str)

# Integer division to get whole decades
decades = age // 10

# Modulus operator to get the remainder (years)
years = age % 10

print("You are " + str(decades) + " decades and " + str(years) + " years old.")
```

  * Integer Division `//`: Divides and returns the whole number result, discarding the remainder.
  * Modulus `%`: Returns the remainder of a division.

-----

## 3\. Conditionals and Imports

### 3.1. Conditionals (`if`, `elif`, `else`)

Allow a program to make decisions and execute different code blocks based on conditions.

  * **`if`**: Executes a code block if its condition is true.
  * **`elif`**: (short for "else if") Checks a new condition if the previous `if`/`elif` was false.
  * **`else`**: Executes a code block if all preceding `if`/`elif` conditions were false.

<!-- end list -->

```python
temp = 75

if temp > 80:
    print("It's too hot!")
elif temp < 60:
    print("It's too cold!")
else:
    print("Enjoy the outdoors!")
```

**Indentation** (typically 4 spaces) is crucial in Python. It defines the code blocks for `if`, `elif`, and `else`.

### 3.2. Comparators and Booleans

  * **Comparators** are used to compare values and result in a Boolean value.
      * `==` : Equal to
      * `!=` : Not equal to
      * `<`  : Less than
      * `>`  : Greater than
      * `<=` : Less than or equal to
      * `>=` : Greater than or equal to
  * **Boolean (`bool`):** A data type with only two possible values: `True` or `False`.

### 3.3. Logical Operators

Used to combine multiple conditions.

  * **`and`**: `True` only if **both** conditions are `True`.
  * **`or`**: `True` if **at least one** condition is `True`.
  * **`not`**: Inverts a Boolean value (`not True` is `False`).

<!-- end list -->

```python
temp = 50
forecast = "sunny"

# Example using 'or'
if temp > 80 or temp < 60:
    print("Stay inside.")

# Example using 'and'
if temp < 80 and forecast != "rainy":
    print("Go outside!")
```

### 3.4. Importing Modules

Python's functionality can be extended by importing modules.

  * The **Python Standard Library** comes with many useful modules.
  * Use the `import` keyword to make a module's functions available.

### Project: Rock, Paper, Scissors Game

A game where the user plays against the computer.

1.  **Static Version:** The computer's choice is hard-coded.
2.  **Randomized Version:** Uses the `random` module to make the computer's choice unpredictable.

<!-- end list -->

```python
# rock_paper_scissors.py (Randomized)
import random

choices = ["rock", "paper", "scissors"]
computer_choice = random.choice(choices)
user_choice = input("Do you want rock, paper, or scissors? ")

print(f"Computer chose: {computer_choice}")

if computer_choice == user_choice:
    print("TIE")
elif (user_choice == "rock" and computer_choice == "scissors") or \
     (user_choice == "paper" and computer_choice == "rock") or \
     (user_choice == "scissors" and computer_choice == "paper"):
    print("YOU WIN")
else:
    print("YOU LOSE")
```

  * `import random`: Imports the random module.
  * `random.choice(sequence)`: Returns a random element from a sequence (like a list).

-----

## 4\. Lists and Loops

### 4.1. Lists

A list is an ordered, mutable (changeable) container that can store a collection of items.

  * Created with square brackets `[]`.
  * Items are separated by commas.
  * Indexing starts at `0`.

<!-- end list -->

```python
# Creating a list
acronyms = ['LOL', 'IDK', 'SMH']

# Accessing an item by index
first_acronym = acronyms[0] # 'LOL'

# Adding an item to the end
acronyms.append('TBH')

# Removing an item by value
acronyms.remove('IDK')

# Removing an item by index
del acronyms[0]

# Checking if an item is in a list
if 'SMH' in acronyms:
    print("It's in the list!")
```

### 4.2. `for` Loops

Used to iterate over a sequence (like a list) and execute a code block for each item.

```python
expenses = [10.50, 8, 5, 15, 20, 5, 3]
total = 0

for expense in expenses:
    total = total + expense

print(f"You spent ${total}")
```

  * The `sum()` built-in function is a shortcut for adding numbers in a list: `total = sum(expenses)`.

### 4.3. The `range()` function

Generates a sequence of numbers, often used with `for` loops to repeat a block of code a specific number of times.

  * `range(stop)`: Goes from `0` up to (but not including) `stop`. E.g., `range(3)` is `0, 1, 2`.
  * `range(start, stop, step)`: A more customizable version.

<!-- end list -->

```python
# Loop 5 times
for i in range(5):
    print(i) # Prints 0, 1, 2, 3, 4
```

### Project: Loan Calculator

Calculates the remaining loan balance over a specified number of months.

```python
# loan.py

money_owed = float(input("How much money do you owe, in dollars? ")) # 50000
apr = float(input("What is the annual percentage rate? ")) # 3
payment = float(input("What will your monthly payment be, in dollars? ")) # 1000
months = int(input("How many months do you want to see results for? ")) # 24

monthly_rate = apr/100/12

for i in range(months):
    interest_paid = money_owed * monthly_rate
    money_owed = money_owed + interest_paid

    if (money_owed - payment < 0):
        print(f"The last payment is {money_owed}")
        print(f"You paid off the loan in {i+1} months")
        break # Exit the loop early

    money_owed = money_owed - payment

    print(f"Paid {payment} of which {interest_paid:.2f} was interest.", end=' ')
    print(f"Now I owe {money_owed:.2f}")

```

  * `break`: A statement that immediately terminates a loop.
  * **f-string formatting**: `:.2f` formats a number to two decimal places.

-----

## 5\. Dictionaries, JSON, and `pip`

### 5.1. Dictionaries (`dict`)

An unordered collection of key-value pairs.

  * Created with curly braces `{}`.
  * Each item consists of a `key: value`.
  * Keys must be unique and are used to look up values.

<!-- end list -->

```python
# Creating a dictionary
acronyms = {'LOL': 'laugh out loud', 'IDK': 'I don't know'}

# Accessing a value by key
definition = acronyms['LOL']

# Adding or updating an item
acronyms['TBH'] = 'to be honest'

# Deleting an item
del acronyms['IDK']

# Safely getting a value to avoid a KeyError
showtime = current_movies.get('The Grinch')
if showtime is None:
    print("Movie not found")
else:
    print(f"The showtime is {showtime}")
```

### 5.2. Nested Data Structures

You can combine lists and dictionaries to represent complex data.

  * A dictionary can have lists as values.
  * A list can contain dictionaries.

<!-- end list -->

```python
# A list of dictionaries
students = [
    {'name': 'Sarah', 'email': 'sarah@example.com'},
    {'name': 'Harry', 'email': 'harry@example.com'}
]

# Looping to access nested data
for student in students:
    print(student['email'])
```

### 5.3. JSON (JavaScript Object Notation)

A lightweight data format used to exchange data, especially with web APIs. Its syntax is very similar to Python's dictionaries and lists.

### 5.4. Web Requests and APIs

  * **API (Application Programming Interface):** A way for different software applications to communicate with each other. Web APIs often return data in JSON format.
  * **HTTP Request:** A request sent from a client (your program) to a web server.
  * The **`requests` library** is the standard for making HTTP requests in Python. It is not part of the standard library and must be installed.

### 5.5. Package Management with `pip`

  * `pip` is the package installer for Python. It downloads and installs packages from the Python Package Index (PyPI).
  * **Install a package:** `pip install requests`
  * **Check `pip` version:** `pip --version`

### 5.6. Virtual Environments (`venv`)

A best practice for managing project dependencies. A `venv` creates an isolated environment where packages can be installed for a specific project, without affecting other projects or the global Python installation.

1.  **Create a venv:**
    ```bash
    # In your project folder
    python3 -m venv venv
    ```
2.  **Activate the venv:**
    ```bash
    # macOS / Linux
    source venv/bin/activate
    # Windows
    .\venv\Scripts\activate
    ```
3.  **Install packages:** `pip install <package_name>`
4.  **Deactivate:** `deactivate`

### Project: Weather Reader

This program fetches live weather data from the OpenWeatherMap API and displays it.

```python
# weather.py
import requests

# URL with API Key and City
api_key = "YOUR_API_KEY"
city = "Orlando"
url = f"[http://api.weatherapi.com/v1/current.json?key=](http://api.weatherapi.com/v1/current.json?key=){api_key}&q={city}&aqi=no"

response = requests.get(url)
weather_json = response.json()

# Drilling down into the nested dictionary
temp = weather_json.get('current').get('temp_f')
description = weather_json.get('current').get('condition').get('text')

print(f"Today's weather in {city} is {description} and {temp} degrees.")
```

-----

## 6\. Functions

### 6.1. Introduction to Functions

A named, reusable block of code that performs a specific task.

  * **Why use functions?**
    1.  **Code Reusability:** Write once, use many times (DRY - Don't Repeat Yourself).
    2.  **Organization:** Group code into logical units, making programs easier to read and manage.

### 6.2. Defining and Calling a Function

  * Use the `def` keyword to define a function.
  * **Parameters:** Variables listed inside the parentheses in the function definition.
  * **Arguments:** The actual values passed to the function when it is called.
  * The `return` statement is used to send a value back from the function.

<!-- end list -->

```python
# Defining a function with parameters
def addition(a, b):
    return a + b

# Main program
# Functions must be defined before they are called
num1 = 10
num2 = 20

# Calling the function and passing arguments
sum_result = addition(num1, num2)
print(sum_result) # Output: 30
```

### 6.3. Variable Scope

  * **Local Scope:** A variable created inside a function is only accessible within that function.
  * **Global Scope:** A variable created in the main body of the program can be accessed anywhere.
  * It's generally better to pass variables into functions as parameters (using local scope) rather than relying on global variables, as it makes code easier to understand and debug.

### 6.4. Organizing with a `main` function

It's a common convention to wrap the main part of your program in a function, often called `main()`.

```python
def roll_dice():
    # ... code to roll dice ...
    return dice_total

def main():
    # Main program logic goes here
    player1_roll = roll_dice()
    player2_roll = roll_dice()
    # ... more logic ...

# Call the main function to start the program
main()
```

-----

## 7\. Classes and Objects (OOP)

### 7.1. Introduction to Object-Oriented Programming (OOP)

A programming paradigm that uses "objects" to represent real-world things.

  * **Object:** An instance of a class. It has:
      * **State:** Properties or attributes (data).
      * **Behavior:** Methods (functions that belong to the object).
  * **Class:** A blueprint or template for creating objects.

### 7.2. Creating a Class

  * Use the `class` keyword.
  * The **`__init__` method** (the constructor) is a special method that runs when an object is created. It's used to initialize the object's properties.
  * The **`self` parameter** refers to the instance of the class (the object itself). It must be the first parameter of any method in a class.

<!-- end list -->

```python
class Robot_Dog:
    # The constructor method
    def __init__(self, name_val, breed_val):
        # Initializing properties (state)
        self.name = name_val
        self.breed = breed_val

    # A method (behavior)
    def bark(self):
        print("Woof Woof!")

# Creating an object (an instance of the class)
my_dog = Robot_Dog("Spot", "Chihuahua")

# Accessing properties and calling methods
print(my_dog.name) # Output: Spot
my_dog.bark()      # Output: Woof Woof!
```

### 7.3. Class Inheritance

A mechanism where one class (the child/derived class) inherits the properties and methods of another class (the parent/base class).

  * Models an **"is-a"** relationship (e.g., a `Robot_Dog` **is a** `Robot`).
  * Promotes code reuse.
  * **Method Overriding:** A child class can provide a specific implementation of a method that is already defined in its parent class.
  * **`super()`:** A function that gives you access to methods in a parent class.

<!-- end list -->

```python
# Parent Class
class Robot:
    def __init__(self, name):
        self.name = name
    def say_name(self):
        print(f"My name is {self.name}!")
    def eat(self):
        print("I'm hungry!")

# Child Class inherits from Robot
class Robot_Dog(Robot):
    # Overriding the 'eat' method
    def eat(self):
        super().eat() # Call the parent's eat method
        print("I like bacon!")

# Create a Robot_Dog object
bud = Robot_Dog("Bud")
bud.say_name() # Inherited from Robot
bud.eat()      # Overridden in Robot_Dog
```

-----

## 8\. Working with Files and Exceptions

### 8.1. Exception Handling

  * **Exception:** An error that occurs during the execution of a program. If unhandled, it will crash the program.
  * **`try...except` block:** Used to catch and handle exceptions, allowing the program to continue running.
  * **`finally`:** A block of code that will always execute, regardless of whether an exception occurred. Often used for cleanup, like closing files.
  * **`raise`:** Used to create and throw an exception deliberately.

<!-- end list -->

```python
try:
    # Code that might cause an error
    value = my_dictionary['non_existent_key']
except KeyError:
    # Code that runs if a KeyError occurs
    print("That key was not found.")
finally:
    print("The try/except block is finished.")
```

### 8.2. Reading and Writing Files

#### File Paths

  * **Absolute Path:** The full path from the root directory (e.g., `/Users/sarah/Desktop/file.txt`).
  * **Relative Path:** The path from the current working directory (e.g., `file.txt` if it's in the same folder).

#### Opening and Closing Files

  * The `with open(...)` statement is the recommended way to work with files. It automatically handles closing the file, even if errors occur.
  * **File Modes:**
      * `'r'`: Read (default).
      * `'w'`: Write (erases the file if it exists, creates it if it doesn't).
      * `'a'`: Append (adds to the end of the file).

<!-- end list -->

```python
# Writing to a file (appending)
acronym = input("What acronym do you want to add? ")
definition = input("What is its definition? ")

with open('acronyms.txt', 'a') as file:
    file.write(f"{acronym} - {definition}\n")


# Reading from a file
try:
    with open('acronyms.txt', 'r') as file:
        for line in file:
            print(line.strip()) # .strip() removes leading/trailing whitespace
except FileNotFoundError:
    print("File not found.")
```

### 8.3. File and Directory Manipulation

The `os` and `shutil` modules provide functions for interacting with the file system.

  * `os.mkdir(path)`: Creates a new directory.
  * `os.path.join(path, name)`: Safely joins path components.
  * `os.scandir(path)`: Lists the contents of a directory.
  * `os.path.isfile(path)`: Checks if a path is a file.
  * `shutil.move(source, destination)`: Moves a file or directory.

### Project: File Organizer

A script that organizes files on the Desktop into subfolders (Images, Documents, Archives) based on their file extension.

```python
# file_organizer.py
import os
import shutil

# Dictionary mapping folder names to file extensions
folders = {
    'Images': ['.jpeg', '.jpg', '.png'],
    'Documents': ['.doc', '.docx', '.pdf', '.txt'],
    'Archives': ['.zip', '.rar']
}

# Get path to Desktop
desktop_path = os.path.join(os.path.expanduser('~'), 'Desktop')

# Create folders if they don't exist
for folder_name in folders:
    folder_path = os.path.join(desktop_path, folder_name)
    if not os.path.exists(folder_path):
        os.mkdir(folder_path)

# Loop through files on the desktop and move them
for file_name in os.listdir(desktop_path):
    original_file_path = os.path.join(desktop_path, file_name)

    if os.path.isfile(original_file_path):
        # Find the correct subfolder for the file
        for folder_name, extensions in folders.items():
            for ext in extensions:
                if file_name.endswith(ext):
                    destination_folder = os.path.join(desktop_path, folder_name)
                    shutil.move(original_file_path, destination_folder)
                    print(f"Moved {file_name} to {folder_name}")

```

```
```
