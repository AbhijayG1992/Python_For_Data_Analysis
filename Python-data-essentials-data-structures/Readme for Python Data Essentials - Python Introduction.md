# Python Data Essentials: Python Introduction

## Course Overview

Hello, everyone. My name is Abhijay , and welcome to my course, **Python Data Essentials: Python Introduction**. I am an software professional (10+ YOE) who loves to teach online. Python is one of the most preferred languages when it comes to data science. 
When you are finished with this course, you will have an understanding of Python concepts and practical skills that are needed for getting started with data science. In this course, we are going to understand the fundamentals and basics of Python concepts that apply to the data science space.

### Major Topics Covered

- **Data Structures**: Learn about lists, dictionaries, tuples, and sets.
- **Operators**: Explore different types of operators in Python.
- **Packages**: Understand how to use and manage packages.
- **Identifiers**: Learn about naming conventions and identifiers in Python.

By the end of this course, you will have a clear understanding of Python fundamentals and basic concepts that apply to the field of data science.

### Prerequisites

Before beginning this course, you should be familiar with basic concepts such as:
- What is programming?
- Why should you learn to program?

From here, you should feel comfortable diving into data science with courses on the Python Data Essentials path. I hope you will join me on this journey to learn Python fundamentals and basic concepts with the **Python Data Essentials: Python Introduction** course.

---
# Python and Data Science

## Course Overview

### Python and Data Science

Hello everybody. Welcome to this class. In this lecture, we are going to do an introduction to Python, and we are going to discuss about Python and data science. So by the end of this lecture, you will have clarity as to what Python is. We are going to discuss the features of Python, different packages that are available for data science, and why Python is preferred for data science.

### Topics Covered

1. **Introduction to Python**:
   - What is Python?
   - Python as a powerful programming language.
   - Open source and freely available, even for commercial usage.
   - Use cases: web applications, desktop applications, automation, data science, and machine learning.

2. **Features of Python**:
   - **Object-Oriented**: Everything in Python is an object.
   - **Interpreted**: Execution is done line-by-line by the Python Interpreter.
   - **Portable**: Write code once and run it anywhere (Windows, Mac, Linux).
   - **Strong Support of Libraries and Packages**: Extensive developer community and availability of various libraries.

3. **Popular Data Science Packages**:
   - **NumPy**: Popular package for computing and data analysis.
   - **Matplotlib**: Powerful visualization package for plotting graphs and visualizing data.
   - **Pandas**: Used for data analysis and manipulation of datasets.
   - **SciPy**: Scientific computing in Python.

4. **Why Python for Data Science?**:
   - Wide range of packages and libraries available for data work.
   - Free to use.
   - Beginner-friendly with simple syntax.

---

## Installing Python

### Hands-on Demo: Installing Python

Hello everybody. Welcome to this class. In this lecture, we are going to install Python on our system. Follow along for a hands-on demo to download and install Python.

#### Installing Python on Windows:

1. **Open Windows PowerShell**:
   - Go to Start and search for PowerShell.
   - Open the PowerShell terminal.

2. **Check for Existing Python Installation**:
   - Run the command: `python3 --version`
   - If Python is not installed, you will see a message indicating that.

3. **Install Python from Microsoft Store**:
   - Run the command: `python3`
   - This will open the Microsoft Store, directing you to the Python app.
   - Click on "Get" to download and install Python.

4. **Verify Python Installation**:
   - Run the command: `python3 --version`
   - You should see the version number of Python installed.

#### Installing Python on Mac:

1. **Download Python**:
   - Search for "Python download" on Google.
   - Click on the official Python website link and download Python.

2. **Install Python**:
   - Double-click on the downloaded `.pkg` file.
   - Follow the on-screen instructions to complete the installation.

3. **Verify Python Installation**:
   - Open the Terminal application.
   - Run the command: `python3 --version`
   - You should see the version number of Python installed.

4. **Using Python Shell**:
   - Log into Python Shell by running the command: `python3`
   - Run simple Python commands within the shell (e.g., `print("Hello Python")`, `2+2`, `2*6`).

### Conclusion

By following these instructions, you should have Python installed and be able to run simple Python commands. The Python shell can be used as an interactive terminal to test and execute Python code.

---

# Different Python IDEs

## Course Overview

### Introduction to IDEs

Hello everybody. Welcome to this class. In this lecture, we are going to talk about different Python IDEs. Before that, we will discuss what IDEs are.

### What are IDEs?

IDE stands for Integrated Development Environment. An IDE is a tool that increases the productivity of developers by providing various features that assist in programming. Although you can use a text editor to write code, an IDE provides additional benefits such as:

- **Syntax Highlighting**: Makes code easier to read and understand.
- **Autocomplete**: Suggests code as you type, saving keystrokes and reducing syntax errors.
- **Debugging**: Tools to find and fix errors in your code.
- **Integrated Version Control**: Built-in support for version control systems like Git.

### Different Python IDEs

We will discuss various Python IDEs available in the market:

1. **PyCharm**:
   - **Official Website**: [JetBrains PyCharm](https://www.jetbrains.com/pycharm/)
   - Developed by JetBrains, PyCharm is a popular IDE with features like syntax highlighting, autocomplete, and debugging. It is available in two versions:
     - **PyCharm Professional Edition**: Paid version with advanced features.
     - **PyCharm Community Edition**: Free, open-source version suitable for learning Python.

2. **Atom IDE**:
   - Atom was maintained by GitHub. However, as of June 8, 2022, GitHub has announced it will no longer focus on Atom.
   - Atom was a popular IDE with features like syntax highlighting and a customizable interface, but it's no longer recommended for future use due to discontinued development.

3. **Visual Studio Code**:
   - **Official Website**: [Visual Studio Code](https://code.visualstudio.com/)
   - Developed by Microsoft, Visual Studio Code is a lightweight yet powerful IDE with features like Git integration, debugging, and a wide range of extensions.

4. **Jupyter Notebook**:
   - **Official Website**: [Jupyter.org](https://jupyter.org/)
   - Jupyter Notebook is a web-based IDE focused on data analysis and visualization. It is popular among data science professionals. It runs in the browser and offers an interactive environment for running Python code.

### Conclusion

By understanding the different Python IDEs and their features, you can choose the one that best suits your needs, whether you are a beginner or an advanced developer. In our course, we will be using Jupyter Notebook due to its popularity and focus on data science.

---
# Installing and Setting up Jupyter Notebook

## Introduction
This guide will walk you through the steps to install and set up Jupyter Notebook on your system.

## Prerequisites
- **Python**: Ensure Python is installed on your system.
- **Pip**: Pip is a package manager for Python packages. It is included with the latest versions of Python.

## Step-by-Step Guide

### 1. Install Jupyter Notebook
1. **Open Terminal (macOS) or PowerShell (Windows)**
2. **Run the following command**:
    ```bash
    pip install jupyter
    ```
    - This command uses the pip package manager to install Jupyter Notebook.
    - You should see a message saying `Successfully installed jupyter`.

### 2. Launch Jupyter Notebook
1. **Run the following command**:
    ```bash
    jupyter notebook
    ```
    - This command will launch Jupyter Notebook in your default web browser.
    - If the browser does not open automatically, copy the URL provided in the terminal and paste it into your browser.

### 3. Create a New Notebook
1. **Navigate to the Jupyter Notebook Interface in Your Browser**:
    - You will see the Jupyter web interface with a folder structure.
2. **Create a New Notebook**:
    - Click on `New` and select `Python 3`.
    - A new tab will open with the Jupyter Notebook interface.

### 4. Jupyter Notebook Interface
1. **Rename the Notebook**:
    - The default notebook name is `Untitled`.
    - Click on the name and rename it (e.g., `First Notebook`), then click `Rename`.
2. **Notebook Menu Bar**:
    - The menu bar contains various options like `File`, `Edit`, etc.
3. **Notebook Toolbar**:
    - The toolbar has buttons for common actions (e.g., save, add cell, delete cell).
    - Hover over each button to see more information.

### 5. Working with Checkpoints
1. **Save and Create Checkpoints**:
    - Click the save button or use the `File` menu to save and create a checkpoint.
    - You will see a message `Checkpoint created`.
2. **Revert to a Checkpoint**:
    - Go to `File` -> `Revert to Checkpoint` to revert to a previously saved version.

### 6. Adding and Running Code Cells
1. **Add a New Cell**:
    - Use the `+` button to add a new cell.
2. **Delete a Cell**:
    - Use the scissor icon to delete a cell.
3. **Run Python Code**:
    - Type Python code in a cell (e.g., `print("Hello World")`).
    - Press `Shift + Enter` to run the code.

### 7. Using Jupyter Notebook as a Calculator
1. **Basic Calculations**:
    - You can perform calculations in a cell (e.g., `2 + 3` or `4 * 2`).
    - Run the cell to see the output.

### 8. Writing  in Jupyter Notebook
1. **Change Cell Type to **:
    - Select a cell and change the type from `Code` to ``.
2. **Writing Text**:
    - Write  text, such as headings (e.g., `# First Notebook`).
    - Press `Shift + Enter` to render the .

### 9. Download and Share the Notebook
1. **Download as PDF**:
    - Go to `File` -> `Download as` -> `PDF` to save and share your notebook.

### Important Note
- **Keep the Console Running**:
    - If you close the terminal/PowerShell where you executed the Jupyter Notebook command, you will not be able to use Jupyter Notebook in your browser. Keep it running in the background.

## Conclusion
You have successfully installed and set up Jupyter Notebook on your system. Enjoy coding and creating your notebooks!

---

# Basics of Python

## Python Identifiers and Literals

Hello everybody. Welcome to this module. In this module, we will cover the following topics:
- Python Identifiers
- Python Literals

We will also discuss expressions and operators later in this module. Let's dive into the topics.

### Identifiers

Identifiers are names given to entities like functions, variables, classes, etc. in Python. They help in identifying and recognizing these entities. Here are some important rules and guidelines for creating identifiers in Python:
1. **Identifiers cannot start with a number.**
2. **Special characters are not allowed in identifiers.**
3. **Reserved words cannot be used as identifiers.**
4. **Identifiers are case-sensitive.**

#### Practical Example

```python
# Example of an identifier
greet = "Hello Python"
print(greet)  # Output: Hello Python 
```
In the above code, greet is an identifier, and "Hello Python" is a literal value assigned to the variable greet.

### Literals

Literals represent raw data assigned to variables or constants. There are different types of literals in Python:

### Numeric Literals:

Integer: Whole numbers.
Float: Numbers with decimal points.

```python
a = 10  # Integer literal
print(type(a))  # Output: <class 'int'>

b = 5.2  # Float literal
print(type(b))  # Output: <class 'float'>
```

### String Literals:

Sequence of characters enclosed in single or double quotes.

```python
greeting = "Hello Python"
print(type(greeting))  # Output: <class 'str'>

greeting_single = 'Hello Python'
print(type(greeting_single))  # Output: <class 'str'>
```

### Boolean Literals:

Represented by True and False.

```python
is_active = True
print(type(is_active))  # Output: <class 'bool'>

is_inactive = False
print(type(is_inactive))  # Output: <class 'bool'>
```
---

# Expressions and Operators in Python

### Introduction

In this module, we will cover the following topics:
- Expressions
- Operators

We will use Jupyter Notebook to demonstrate these concepts practically.

### Expressions

An expression is a combination of operators and operands that work together to produce a computed value. For example:

```python
6 + 6  # Output: 12
```

In this example, 6 and 6 are operands, and + is an operator. The expression evaluates to a single output, which is 12.

---
## Types of Operators

In Python, there are three main types of operators:

#### Arithmetic Operators
#### Comparison Operators
#### Logical Operators

We will explore each of these in detail.

### Arithmetic Operators
Arithmetic operators perform mathematical operations such as addition, subtraction, multiplication, etc. Here are the different types of arithmetic operators:

#### Addition
```python
a = 10
b = 4
print(a + b)  # Output: 14
```
#### Subtraction
```python
print(a - b)  # Output: 6
```
#### Multiplication

```python
print(a * b)  # Output: 40
```

#### Division

```python
print(a / b)  # Output: 2.5
```
#### Modulo
The modulo operator returns the remainder after division.

```python
print(a % b)  # Output: 2
```
#### Floor Division
The floor division operator returns the division result adjusted to the left in the number line.

```python
print(a // b)  # Output: 2
print((-a) // b)  # Output: -3
```
#### Exponent
The exponent operator raises the left operand to the power of the right operand.

```python
print(a ** b)  
```
---
# Comparison Operators in Python

## Introduction

Hello everybody. In this lecture, we will understand and explore how comparison operators work in Python using Jupyter Notebook.

## Comparison Operators

Comparison operators compare the values of two operands and return a Boolean result (True or False). Below are the types of comparison operators in Python:

### Equal to (`==`)

```python
a = 10
b = 4
c = 4

print(a == b)  # Output: False
print(b == c)  # Output: True
```

Not Equal to (!=)
```python
print(b != c)  # Output: False
```
Greater than (>)
```python
print(b > c)  # Output: False
print(a > c)  # Output: True
```
Less than (<)
```python
print(b < c)  # Output: False
print(a < c)  # Output: False
```
Greater than or Equal to (>=)
```python
print(b >= c)  # Output: True
```
Less than or Equal to (<=)
```python
print(b <= c)  # Output: True
```
#### Summary of Comparison Operators
Comparison operators evaluate conditions and return Boolean values. They help in decision-making processes by comparing the values of variables.

#### Logical Operators in Python
Introduction
Hello everybody. In this lecture, we will understand and explore logical operators that exist in Python using Jupyter Notebook.

#### Logical Operators
Logical operators are used in decision-making and work on Boolean operands. There are three types of logical operators:

#### Logical AND (and)
The and operator returns True if both operands are True; otherwise, it returns False.

```python
print(True and True)   # Output: True
print(True and False)  # Output: False
```
#### Logical OR (or)
The or operator returns True if at least one operand is True; otherwise, it returns False.

```python
print(True or False)   # Output: True
print(False or False)  # Output: False
```
#### Logical NOT (not)
The not operator inverts the Boolean value.

```python
print(not True)   # Output: False
print(not False)  # Output: True
```
Using Logical Operators with Expressions
Logical operators can also be used with expressions.

```python
a = 10
b = 4
c = 4
```
#### Logical AND
```python
print((b >= c) and (a <= c))  # Output: False
```
#### Logical OR
```python
print((b >= c) or (a <= c))  # Output: True
````
---
# Python Packages and Data Structures

## Introduction

Hello everybody, and welcome to this class. In this module, we will cover the following topics:
- Python Packages
- Python Data Structures (Lists, Tuples, Sets)

We will start by discussing Python packages and then move on to various data structures in Python.

## Python Packages

### What are Packages?

We, as humans, like to organize everything, whether it's our clothes, books, files, or code. In Python, we organize code using modules and packages. Here’s a breakdown:
- **Modules:** These are individual Python files containing variables, functions, and classes that can be imported and reused in other Python files.
- **Packages:** A group of related modules that serve a common functionality.

### Importance of Packages

Packages enable better organization and code reusability. For instance, in a banking application, all modules related to savings account operations can be grouped into a single package.

### Creating and Using Packages

- **Developers can create their own packages.**
- **Third-party packages** built by others can be used.
- **Python Standard Library**: Comes with numerous packages pre-installed for developers’ use.

### Example

If you're building a banking application, you might create a package like:

banking/ init.py savings.pyloans.pyaccounts.py

### Summary
Python Packages: Groups of related modules serving common functionalities, which help in organizing code efficiently.

# Using Packages in Python

## Introduction

In this module, we will cover how to use and install packages in Python. We will perform a demo to understand the process of using packages that may or may not be installed on your system.

## Demo: Using Packages in Python

### Step 1: Search for the Package

1. Open your web browser and go to Google.
2. Search for "pypi python" to find the Python Package Index (PyPI) website.
3. Click on the first link, which should be `pypi.org`.

### Step 2: Search for a Specific Package

1. On the PyPI website, use the search box to search for the package "camelcase".
2. Select the first result, "camelcase 0.2".

### Step 3: Understanding the Package

The "camelcase" package is used to convert a string to camelcase. The project home page provides sample code that demonstrates its basic usage.

### Step 4: Installing the Package

1. Open your coding editor, such as Jupyter Notebook.
2. To use the package, you first need to install it. The installation command provided on the PyPI project page is `pip install camelcase`.

```bash
pip install camelcase
```
---
# Using Packages in Python

## Introduction

In this module, we will cover how to use and install packages in Python. We will perform a demo to understand the process of using packages that may or may not be installed on your system.

## Demo: Using Packages in Python

### Step 1: Search for the Package

1. Open your web browser and go to Google.
2. Search for "pypi python" to find the Python Package Index (PyPI) website.
3. Click on the first link, which should be `pypi.org`.

### Step 2: Search for a Specific Package

1. On the PyPI website, use the search box to search for the package "camelcase".
2. Select the first result, "camelcase 0.2".

### Step 3: Understanding the Package

The "camelcase" package is used to convert a string to camelcase. The project home page provides sample code that demonstrates its basic usage.

### Step 4: Installing the Package

1. Open your coding editor, such as Jupyter Notebook.
2. To use the package, you first need to install it. The installation command provided on the PyPI project page is `pip install camelcase`.

```bash
pip install camelcase
```

### Step 5: Running the Code
1. In Jupyter Notebook, open a terminal by clicking on "New" and then "Terminal".

2. Run the install command:

```bash
pip install camelcase
```

3. After successful installation, you should see a success message indicating the package version.

### Step 6: Using the Package in Your Code
Switch back to your Jupyter Notebook and use the following code to utilize the camelcase package:


```python
import camelcase

# Create an instance of the CamelCase class
c = camelcase.CamelCase()

# Create a string
s = "how are you?"

# Convert the string to camelcase
print(c.hump(s))  # Output: How Are You?
```
### Step 7: Re-run the Code
After installing the package, re-run the code. You should now see the camelcased output.

Additional Information
Data Science Packages
There are many packages available for data science. These can be installed individually using pip or through the Anaconda distribution.

#### Anaconda Distribution
Anaconda is a Python distribution that comes pre-installed with many packages needed for data science, such as:

NumPy

SciPy

Jupyter Notebook

pandas

#### Package Managers
pip: The standard Python package manager used for installing and managing packages.

Conda: Anaconda's package manager used for managing packages in the Anaconda distribution.

#### Summary
To summarize, in this module we have covered:

Searching and Installing Packages: Using the PyPI website and pip command.

Using Installed Packages: Demonstrating the camelcase package in a Python code.

Data Science Packages and Anaconda: An overview of using Anaconda for pre-installed data science packages and using Conda as a package manager.

---

# Python Data Structures

Hello everybody. Welcome to this class. Let us start discussing Python data structures. Today, we live in an information age wherein there is a lot of data around us. It is important that we should be able to organize, process, and work with data in the most efficient way. This is where data structures come into the picture. Data structures allow us to organize, process, and work with the data. They make it easy for us to work with data in an easy and efficient manner. 

There are some built-in data structures in Python:
- Lists
- Tuples
- Sets

## Lists
## What Are Lists in Python

Welcome to this class on lists. We are going to do a demo in this class wherein we are going to discuss how to create lists. We will cover how to use them in your program and access individual elements as well. We will discuss the different characteristics of lists, enabling you to make better decisions about when to use the list data structure.

### Creating Lists

Here are some examples of creating lists in Python:

```python
# Creating a list of names
my_list = ['Alice', 'Bob', 'Charlie']
print(my_list)  # Output: ['Alice', 'Bob', 'Charlie']
print(type(my_list))  # Output: <class 'list'>

# Creating a list of numbers
number_list = [1, 2, 3, 4, 5]
print(number_list)  # Output: [1, 2, 3, 4, 5]
print(type(number_list))  # Output: <class 'list'>

# Creating a mixed data type list
mixed_list = [1, 'John', 2.5]
print(mixed_list)  # Output: [1, 'John', 2.5]
print(type(mixed_list))  # Output: <class 'list'>

# Creating a nested list
nested_list = [1, 2, 3, ['a', 'b', 'c']]
print(nested_list)  # Output: [1, 2, 3, ['a', 'b', 'c']]
print(type(nested_list))  # Output: <class 'list'>

# Creating an empty list
empty_list = []
print(empty_list)  # Output: []
print(type(empty_list))  # Output: <class 'list'>
```

#### Accessing Elements in Lists
Lists are represented in memory and can be accessed using indexing. Python supports positive and negative indexing.
Positive indexing starts at 0
Negative indexing starts at -1

```python
# Positive indexing
names = ['John', 'Jane', 'Doe']
print(names[0])  # Output: John

# Negative indexing
print(names[-1])  # Output: Doe

# Accessing elements in a nested list
nested_list = [1, 2, 3, ['a', 'b', 'c']]
print(nested_list[3][1])  # Output: b
```
Mutable: Lists can be modified.

```python
my_list = ['Alice', 'Bob', 'Charlie']
my_list[0] = 'Jonny'
print(my_list)  # Output: ['Jonny', 'Bob', 'Charlie']

# Appending elements
my_list.append('Rob')
print(my_list)  # Output: ['Jonny', 'Bob', 'Charlie', 'Rob']
Ordered: Lists maintain the order of elements.
```
```python
print(my_list)  # Output: ['Jonny', 'Bob', 'Charlie', 'Rob']
Allows Duplicates: Lists can have duplicate elements.
```
```python
duplicate_list = ['Andy', 'Andy']
print(duplicate_list)  # Output: ['Andy', 'Andy']
```

#### Real-World Example of Lists
You can use lists to store items in an online shopping cart. Lists are a good choice for this because:
They are mutable, allowing items to be added or removed as needed.
They provide an ordered collection of items, preserving the order in which items were added to the cart. This is useful for displaying items to the customer and keeping track of the sequence of events leading up to the purchase.

```python
shopping_cart = ['apple', 'banana', 'cherry']
shopping_cart.append('date')
print(shopping_cart)  # Output: ['apple', 'banana', 'cherry', 'date']
```

## Tuples
### What Are Tuples
Hello everybody. Welcome to this class. In this class, we are going to do a hands‑on demo wherein we are going to discuss all about tuples. We are going to cover how you can create your own set of tuples, how you can use them in your programs, and we will even discuss the characteristics of tuples. Understanding the characteristics will enable you to make better decisions as to how and when to use this data structure in your Python programs. So let's get started.

### Creating Tuples
Tuples are data structures that allow you to store multiple items. Here is how you can create a tuple:

```python
# Creating a tuple with three names of fruits
my_tuple = ('apple', 'banana', 'cherry')
print(my_tuple)  # Output: ('apple', 'banana', 'cherry')
print(type(my_tuple))  # Output: <class 'tuple'>
```

Single Element Tuple
To create a tuple with a single element, you need to include a comma after the element:
```python
# Incorrect way (creates a string)
single_element_tuple = ('apple')
print(type(single_element_tuple))  # Output: <class 'str'>
```
```python
# Correct way (creates a tuple)
single_element_tuple = ('apple',)
print(type(single_element_tuple))  # Output: <class 'tuple'>
```
Mixed Type Tuple
You can create tuples with mixed data types:

```python
mixed_tuple = ('apple', 'banana', 'cherry', 10, 11.5)
print(mixed_tuple)  # Output: ('apple', 'banana', 'cherry', 10, 11.5)
```

Empty Tuple
Creating an empty tuple:

```python
empty_tuple = ()
print(empty_tuple)  # Output: ()
print(type(empty_tuple))  # Output: <class 'tuple'>
```

#### Accessing Elements in Tuples
Tuples support indexing similar to lists:

```python
# Accessing elements using positive index
print(my_tuple[0])  # Output: apple
```

```python
# Accessing elements using negative index
print(my_tuple[-1])  # Output: cherry
```
```python
# Checking existence of an element
print('apple' in my_tuple)  # Output: True
print('watermelon' in my_tuple)  # Output: False
```


Tuple Packing and Unpacking
Tuple Packing
Combining multiple values into a single tuple:

```python
name = 'John'
age = 25
city = 'New York'
packed_tuple = (name, age, city)
print(packed_tuple)  # Output: ('John', 25, 'New York')
```

Tuple Unpacking
Extracting individual values from a tuple:

```python
person = ('John', 25, 'New York')
name, age, city = person
print(name)  # Output: John
print(age)  # Output: 25
print(city)  # Output: New York
```

Using Tuples in Functions
Tuples can be used to return multiple values from a function:

```python
def get_user_info():
    return ('John Doe', 30, 'Los Angeles')

name, age, city = get_user_info()
print(name)  # Output: John Doe
print(age)  # Output: 30
print(city)  # Output: Los Angeles
```

#### Characteristics of Tuples
Immutable: Tuples cannot be modified after creation. 

```python
my_tuple = ('apple', 'banana', 'cherry')
try:
    my_tuple[0] = 'orange'
except TypeError as e:
    print(e)  # Output: 'tuple' object does not support item assignment
```
Ordered: Tuples maintain the order of elements.

```python
print(my_tuple)  # Output: ('apple', 'banana', 'cherry')
```

Allows Duplicates: Tuples can have duplicate elements.

```python
duplicate_tuple = ('Andy', 'Andy')
print(duplicate_tuple)  # Output: ('Andy', 'Andy')
```

Real-World Use Cases of Tuples
Since tuples are ordered and immutable, 
they are often used to store data that needs to be grouped together and has an unchanging structure. A common example is storing geographic coordinates for a location:


```python
# Latitude and Longitude of a location
coordinates = (40.7128, -74.0060)
print(coordinates)  # Output: (40.7128, -74.0060)
```

Tuples are a good choice for this kind of data because they avoid accidental changes that could cause errors in an application that relies on them.

## Sets
## What Are Sets

Hello everybody. Welcome to this class. In this class, we are going to cover sets, wherein we are going to do a hands-on demo, and we are going to understand this data structure completely. We are going to discuss how you can create your own set, how you can use them in your Python program, and we will even discuss the characteristics of sets. So let's get started.

## Creating Sets

A set is a data structure that allows you to store multiple items with unique characteristics compared to lists and tuples.

### Creating a Set

Here's how you can create a set:

```python
# Creating a set of email IDs
my_set = {'john@example.com', 'jane@example.com', 'doe@example.com'}
print(my_set)  # Output: {'john@example.com', 'jane@example.com', 'doe@example.com'}
print(type(my_set))  # Output: <class 'set'>
```

Set with Numbers
You can create a set with a list of numbers:

```python
number_set = {1, 2, 13, 4, 5.0, 6.7}
print(number_set)  # Output: {1, 2, 4, 5.0, 6.7, 13}
print(type(number_set))  # Output: <class 'set'>
```

Set with Mixed Types
You can create a set with mixed data types:

```python
mixed_set = {1, 1.5, 'Hello'}
print(mixed_set)  # Output: {1, 1.5, 'Hello'}
print(type(mixed_set))  # Output: <class 'set'>
```

Creating an Empty Set
To create an empty set, you must use the set() function:

```python
empty_set = set()
print(empty_set)  # Output: set()
print(type(empty_set))  # Output: <class 'set'>
```
#### Accessing Elements in Sets
Sets do not support indexing. If you try to use indexing with a set, you will get an error.

Iterating Through a Set
You can iterate through a set using a for loop:

```python
for email in my_set:
    print(email)
# Output:
# john@example.com
# jane@example.com
# doe@example.com
```
#### Using the in Operator
You can use the in and not in operators to check if an element exists in a set:

```python
# Check if element exists in set
print('john@example.com' in my_set)  # Output: True
print('john22@example.com' in my_set)  # Output: False
```
```python
# Check if element does not exist in set
print('john@example.com' not in my_set)  # Output: False
print('john22@example.com' not in my_set)  # Output: True
```
#### Characteristics of Sets
Immutable: Once a set is created, you cannot modify its elements.

```python
my_set = {'apple', 'banana', 'cherry'}
try:
    my_set[0] = 'orange'
except TypeError as e:
    print(e)  # Output: 'set' object does not support item assignment
Unordered: Sets do not maintain the order of elements.
```

```python
print(my_set)  # Output: {'banana', 'cherry', 'apple'}
No Duplicates: Sets do not allow duplicate elements.
```
```python
my_set = {'john@example.com', 'jane@example.com', 'john@example.com'}
print(my_set)  # Output: {'john@example.com', 'jane@example.com'}
```

#### Real-World Use Cases of Sets
Since sets are unordered and do not allow duplicate items, you can use them to store and maintain unique email addresses in your application. Sets are often used to store lists of unique items where the order is not important. For example, in a mailing list, ensuring there are no duplicate addresses is crucial to avoid sending multiple emails to the same recipient, which could be seen as spam and damage the sender's reputation.

Example: Mailing List
```python
email_list = ['john@example.com', 'jane@example.com', 'doe@example.com']
email_set = set(email_list)
print(email_set)  # Output: {'john@example.com', 'jane@example.com', 'doe@example.com'}
```
## Summary
So we have reached the end of the module, and we have covered and learned a lot. Let us summarize our learnings:

Python Packages: Python packages are fundamental to programming, especially for organizing large projects.

Data Structures: We covered lists, tuples, and sets, which are crucial for programming.

Key Points

### Lists:
#### Can be created with mixed data types.
#### Supports nested lists and empty lists.
#### Allows indexing and modifying elements.
#### Ordered and allows duplicates.

### Tuples:
#### Can be created with mixed data types.
#### Allows indexing and checking element existence with in operator.
#### Immutable and ordered.
#### Allows duplicates.

### Sets:
#### Can be created with mixed data types.
#### Allows checking element existence with in operator.
#### Immutable after creation.
#### Unordered and does not allow duplicates.

---
