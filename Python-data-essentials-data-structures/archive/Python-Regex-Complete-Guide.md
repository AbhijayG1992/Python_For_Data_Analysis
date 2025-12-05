## 📅 Regular Expressions Course Schedule

### 🔍 PYTHON REGULAR EXPRESSIONS

| Day            | Module                                     | Chapter                        | Topic                                                                                           |
|----------------|--------------------------------------------|--------------------------------|-------------------------------------------------------------------------------------------------|
| Day 1          | Introduction to Regular Expressions        | Regex Basics                   | Basic Concepts, Literal Characters, Case-Sensitivity                                            |
| Day 1          | Introduction to Regular Expressions        | Regex Basics                   | Special Characters, Shorthand Character Classes, **Revision: Regex Fundamentals**               |
| Day 2          | Introduction to Regular Expressions        | Quantifiers                    | Repetition (Quantifiers), Practical Examples, Hex Color Code Pattern                            |
| Day 2          | Introduction to Regular Expressions        | Quantifiers                    | Practice Exercises, **Revision: Quantifiers**                                                   |
| Day 3          | Using Regex in Python                      | re Module                      | Core Functions (search, match, fullmatch, findall)                                              |
| Day 3          | Using Regex in Python                      | re Module                      | Core Functions (sub, subn, split, compile, escape)                                              |
| Day 4          | Using Regex in Python                      | Match Objects                  | The Match Object, Regex Flags, Practical Examples                                               |
| Day 4          | Using Regex in Python                      | Match Objects                  | **Revision: re Module Functions**                                                               |
| Day 5          | Parsing and Extracting Data                | Data Extraction                | Reading Files and Finding Patterns, Extracting Specific Data                                    |
| Day 5          | Parsing and Extracting Data                | Data Extraction                | Non-Capturing Groups, **Revision: Data Extraction**                                             |
| Day 6          | Data Validation and Sanitization           | Input Validation               | Validating User Input, Sanitizing User Input                                                    |
| Day 6          | Data Validation and Sanitization           | Input Validation               | Preventing Code Injection, **Revision: Validation Techniques**                                  |
| Day 7          | Data Cleaning and Transformation           | Advanced Patterns              | Lookahead and Lookbehind Assertions, Standardizing Text Data                                    |
| Day 7          | Data Cleaning and Transformation           | Advanced Patterns              | Hiding Sensitive Data, **Revision: Data Transformation**                                        |
| Day 8          | Optimizing Regex Patterns                  | Performance                    | Greedy vs. Non-Greedy Matching, Using re.DEBUG                                                  |
| Day 8          | Optimizing Regex Patterns                  | Performance                    | When to Use Simple String Methods, **Course Review and Best Practices**                         |

---

Here are detailed notes formatted for a `README.md` file, based on the provided course transcript.

````markdown
# Working with Regular Expressions in Python - Course Notes

This document contains detailed notes from the course "Working with Regular Expressions in Python" by Maaike van Putten. The notes are organized by module and cover the key concepts, functions, and code examples for using regex in Python.

## Course Information
* **Author:** Maaike van Putten
* **Level:** Intermediate
* **Duration:** 1h 23m
* **Last Updated:** May 2025

---

## 1. Introduction to Regular Expressions (Regex)

A **Regular Expression** (or **Regex**) is a sequence of characters that defines a search pattern. It's used to check if a string contains a specific pattern, for tasks like:
* Searching for text in a file.
* Validating data formats (email addresses, phone numbers, zip codes).
* Finding and replacing text.
* Parsing structured data from unstructured text.

### 1.1. Basic Concepts
* **Literal Characters:** The simplest regex consists of literal characters that match themselves. The pattern `sight` will match the substring "sight" in "Pluralsight".
* **Case-Sensitivity:** Regex is case-sensitive by default. `Sight` will not match `sight`.

### 1.2. Special Characters
Special characters have meanings beyond their literal value, allowing for abstract and powerful patterns.

| Character / Syntax | Name                  | Description                                                                                                    | Example                                     |
| :----------------- | :-------------------- | :------------------------------------------------------------------------------------------------------------- | :------------------------------------------ |
| `.`                | Dot / Wildcard        | Matches any single character except a newline (`\n`).                                                          | `f.n` matches `fun` and `fan`.              |
| `^`                | Caret / Start Anchor  | Asserts the start of the string (or line in MULTILINE mode).                                                   | `^Hello` matches a string that starts with "Hello". |
| `$`                | Dollar / End Anchor   | Asserts the end of the string (or line in MULTILINE mode).                                                     | `world$` matches a string that ends with "world". |
| `\`                | Backslash / Escape    | Escapes a special character to treat it as a literal.                                                          | `\.` matches a literal dot character.       |
| `[...]`            | Character Class / Set | Matches any single character within the brackets. Ranges can be used.                                          | `gr[ae]y` matches `gray` and `grey`.        |
| `[^...]`           | Negated Set           | Matches any single character **not** in the brackets.                                                          | `[^abc]` matches any character except 'a', 'b', or 'c'. |
| `(...)`            | Group                 | Groups multiple characters to be treated as a single unit.                                                     | `(ha)+` matches `ha`, `haha`, etc.          |
| `|`                | Or / Alternation      | Acts as an OR operator, matching the expression before or after it.                                            | `abc|def` matches `abc` or `def`.           |

### 1.3. Shorthand Character Classes

| Shorthand | Represents   | Description                                           |
| :-------- | :----------- | :---------------------------------------------------- |
| `\d`      | `[0-9]`      | Any decimal digit.                                    |
| `\D`      | `[^0-9]`     | Any character that is **not** a decimal digit.        |
| `\s`      | `[...]`      | Any whitespace character (space, tab, newline).       |
| `\S`      | `[^...]`     | Any character that is **not** a whitespace character. |
| `\w`      | `[a-zA-Z0-9_]` | Any alphanumeric character (word character) plus underscore. |
| `\W`      | `[^a-zA-Z0-9_]` | Any character that is **not** a word character.       |
| `\b`      | Word Boundary| The beginning or end of a word (a non-word character next to a word character). |

### 1.4. Repetition (Quantifiers)

Quantifiers specify how many times a character, group, or class must be present.

| Quantifier  | Description                 | Example                                     |
| :---------- | :-------------------------- | :------------------------------------------ |
| `+`         | One or more times           | `\d+` matches one or more digits.           |
| `*`         | Zero or more times          | `\d*` matches zero or more digits.          |
| `?`         | Zero or one time (optional) | `colou?r` matches `color` and `colour`.     |
| `{n}`       | Exactly `n` times           | `\d{3}` matches exactly three digits.      |
| `{n,}`      | At least `n` times          | `\d{2,}` matches two or more digits.        |
| `{n,m}`     | Between `n` and `m` times   | `\d{2,4}` matches 2, 3, or 4 digits.       |

#### Example: Hex Color Code
To match a hex color code like `#ABCDEF` or `#123`:
```python
# Pattern explanation:
# ^#            - Starts with a '#'
# (             - Start outer group
#   (?:           - Start inner non-capturing group
#     [a-fA-F0-9] - Any hex character
#   ){3}          - Repeated exactly 3 times
# )             - End outer group
# {1,2}         - The outer group is repeated once or twice (for 3 or 6 chars)
# $             - End of the string
pattern = r'^#((?:[a-fA-F0-9]){3}){1,2}$'
````

-----

## 2\. Using Regex in Python (`re` module)

Python's built-in `re` module provides functions and support for working with regular expressions.

### 2.1. Core Functions

| Function          | Description                                                                 | Returns                                             |
| :---------------- | :-------------------------------------------------------------------------- | :-------------------------------------------------- |
| `re.search()`     | Scans the string for the **first** location where the pattern produces a match. | A `Match` object if found, otherwise `None`.        |
| `re.match()`      | Matches the pattern **only at the beginning** of the string.                | A `Match` object if found, otherwise `None`.        |
| `re.fullmatch()`  | Matches the pattern against the **entire** string.                          | A `Match` object if found, otherwise `None`.        |
| `re.findall()`    | Finds all **non-overlapping** matches of the pattern in the string.         | A `list` of all matches as strings.                 |
| `re.sub()`        | Replaces all occurrences of the pattern with a replacement string.          | The new, modified string.                           |
| `re.subn()`       | Same as `sub()`, but also returns the number of substitutions made.         | A `tuple` `(new_string, number_of_subs)`.           |
| `re.split()`      | Splits the string by the occurrences of the pattern.                        | A `list` of substrings.                             |
| `re.compile()`    | Compiles a regex pattern into a regex object for more efficient reuse.      | A `Pattern` object.                                 |
| `re.escape()`     | Escapes special characters in a string.                                     | The escaped string.                                 |

```python
import re

text = "The price is $19.99, but the offer ends today."
# search()
match = re.search(r'\$\d+\.\d{2}', text)
if match:
    print(f"Found a match: {match.group(0)}") # Output: Found a match: $19.99

# findall()
prices = re.findall(r'\d+', text)
print(f"Numbers found: {prices}") # Output: Numbers found: ['19', '99']

# sub()
new_text = re.sub(r'price', 'cost', text)
print(new_text) # Output: The cost is $19.99, but the offer ends today.
```

### 2.2. The `Match` Object

Returned by `search`, `match`, and `fullmatch` upon a successful match. It contains information about the match.

  * **`match.group(n)`**: Returns the matched substring. `group(0)` returns the entire match. `group(1)`, `group(2)`, etc., return the captured groups.
  * **`match.groups()`**: Returns a tuple containing all the captured groups.
  * **`match.start()`**: Returns the starting index of the match.
  * **`match.end()`**: Returns the ending index of the match.
  * **`match.span()`**: Returns a tuple `(start, end)` of the match.

<!-- end list -->

```python
import re

text = "My phone number is 555-123-4567."
# Capture area code and the rest of the number separately
match = re.search(r'(\d{3})-(\d{3}-\d{4})', text)

if match:
    print(f"Full match: {match.group(0)}")   # 555-123-4567
    print(f"Area Code: {match.group(1)}")    # 555
    print(f"Main Number: {match.group(2)}")  # 123-4567
    print(f"All groups: {match.groups()}")   # ('555', '123-4567')
    print(f"Span: {match.span()}")           # (19, 31)
```

### 2.3. Regex Flags

Flags modify the behavior of the regex engine. They are passed as an optional last argument.

| Flag               | Description                                                        |
| :----------------- | :----------------------------------------------------------------- |
| `re.IGNORECASE` or `re.I` | Makes the pattern case-insensitive.                                |
| `re.DOTALL` or `re.S`     | Allows `.` to match any character, **including** a newline.        |
| `re.MULTILINE` or `re.M`  | Allows `^` and `$` to match at the beginning and end of each line, not just the whole string. |
| `re.UNICODE` or `re.U`    | Makes character classes like `\w`, `\s`, `\d` work with all unicode characters. |

-----

## 3\. Parsing and Extracting Data

### 3.1. Reading Files and Finding Patterns

A common use case is to read a file and extract information. It's memory-efficient to read a file line-by-line.

```python
# Finding the first occurrence of a word in a file
import re

try:
    with open('sample.txt', 'r') as file:
        for line_num, line in enumerate(file, 1):
            if re.search(r'error', line, re.IGNORECASE):
                print(f"Found 'error' on line {line_num}: {line.strip()}")
                break # Stop after the first match
except FileNotFoundError:
    print("File not found.")
```

### 3.2. Extracting Specific Data (e.g., Product Codes)

Regex is excellent for extracting structured data like product codes, file names, or emails from unstructured text.

```python
import re

text = "We have product SK-45-B2 and another one, PRD-99-C3."
# Pattern for product codes like XX-NN-XX
product_codes = re.findall(r'\b[A-Z]{2}-\d{2}-[A-Z]\d\b', text)
print(product_codes) # Output: ['SK-45-B2', 'PRD-99-C3']
```

  * **Non-Capturing Groups `(?:...)`:** Use this when you need to group a pattern (e.g., for a quantifier) but don't want to capture it as a separate group in the match results. This is useful for avoiding unintended captures when using `findall()`.

-----

## 4\. Data Validation and Sanitization

### 4.1. Validating User Input

Regex ensures that user-provided data conforms to a required format.

```python
# Function to validate a username
def validate_username(username):
    # Must start with a letter, followed by word characters. 3-15 chars long.
    pattern = r'^[a-zA-Z][\w-]{2,14}$'
    if re.fullmatch(pattern, username):
        return True
    return False

print(validate_username("Mary123"))   # True
print(validate_username("123Mary"))   # False
print(validate_username("M-"))        # False
```

### 4.2. Sanitizing User Input to Prevent Code Injection

A crucial security practice. Regex can be used to remove or escape potentially malicious characters from user input before it's processed.

```python
import re

def sanitize_input(data):
    # Remove characters that could be used for SQL injection or XSS
    return re.sub(r'[;\'"()<>]', '', data)

user_input = "Robert'); DROP TABLE students;--"
sanitized = sanitize_input(user_input)
print(sanitized) # Output: Robert DROP TABLE students--

# Note: For SQL injection, always prefer parameterized queries over regex sanitization.
# Regex is a good defense-in-depth measure.
```

-----

## 5\. Data Cleaning and Transformation

### 5.1. Lookahead and Lookbehind Assertions

These are zero-width assertions that allow you to match a pattern only if it's preceded or followed by another pattern, without including that other pattern in the match itself.

  * **Positive Lookahead `(?=...)`**: Asserts that what follows the current position in the string must match the pattern.
  * **Positive Lookbehind `(?<=...)`**: Asserts that what precedes the current position must match the pattern.

<!-- end list -->

```python
import re

text = "The price is $100 and the amount is 200."
# Find numbers that are preceded by a dollar sign
prices = re.findall(r'(?<=\$)\d+', text)
print(prices) # Output: ['100']
```

### 5.2. Standardizing Text Data

Regex is powerful for cleaning text data for analysis (e.g., Natural Language Processing).

  * Removing punctuation.
  * Converting text to a standard case (e.g., lowercase).
  * Tokenizing (splitting text into words).

<!-- end list -->

```python
import re

text = "Hello, world! This is a test."
# Remove punctuation
text = re.sub(r'[^\w\s]', '', text)
# Convert to lowercase
text = text.lower()
# Tokenize into words
words = re.split(r'\s+', text)
print(words) # Output: ['hello', 'world', 'this', 'is', 'a', 'test', '']
```

### 5.3. Hiding (Redacting) Sensitive Data

Use `re.sub()` to find and replace sensitive information like credit card numbers or email addresses with a placeholder.

```python
import re

text = "Contact me at john.doe@email.com or on my card 4111-2222-3333-4444."
# Redact email
redacted_text = re.sub(r'\b[\w.-]+@[\w.-]+\.\w{2,}\b', '[REDACTED_EMAIL]', text)
# Redact credit card
redacted_text = re.sub(r'\b\d{4}-\d{4}-\d{4}-\d{4}\b', '[REDACTED_CC]', redacted_text)

print(redacted_text)
# Output: Contact me at [REDACTED_EMAIL] or on my card [REDACTED_CC].
```

-----

## 6\. Optimizing Regex Patterns

### 6.1. Greedy vs. Non-Greedy (Lazy) Matching

  * **Greedy (Default):** Quantifiers (`*`, `+`, `{n,m}`) try to match as much text as possible.
  * **Non-Greedy / Lazy:** Add a `?` after the quantifier (`*?`, `+?`, `{n,m}?`) to make it match as little text as possible.

<!-- end list -->

```python
import re

text = "<p>First paragraph.</p><p>Second paragraph.</p>"
# Greedy match
greedy_match = re.search(r'<p>.*</p>', text)
print(greedy_match.group(0)) # Output: <p>First paragraph.</p><p>Second paragraph.</p>

# Non-greedy match
non_greedy_match = re.search(r'<p>.*?</p>', text)
print(non_greedy_match.group(0)) # Output: <p>First paragraph.</p>
```

### 6.2. Using `re.DEBUG`

A flag that prints detailed debugging information about how a pattern is compiled. This is useful for understanding performance issues or unexpected behavior.

```python
import re
# The re.DEBUG flag will print compilation details to the console when the script runs
pattern = re.compile(r'\d+', re.DEBUG)
```

### 6.3. When to Use Simple String Methods

For simple cases, built-in string methods are often faster and more readable than regex.

  * `text.startswith('prefix')` vs. `re.match('prefix', text)`
  * `text.endswith('suffix')` vs. `re.search('suffix$', text)`
  * `'substring' in text` vs. `re.search('substring', text)`
  * `text.replace('old', 'new')` vs. `re.sub('old', 'new', text)`

**Rule of thumb:** If you don't need the power of patterns (special characters, quantifiers), use a string method.

```
```
