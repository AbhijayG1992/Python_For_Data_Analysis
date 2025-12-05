# 🔍 Regular Expressions - Complete Guide (Advanced Python)

## 📅 Regex Course Schedule

| Day | Topics | Key Concepts |
|-----|--------|--------------|
| **Day 1** | Regex Basics, Literal Characters, Special Characters | Patterns, wildcards, character classes |
| **Day 2** | Quantifiers, Repetition Patterns | +, *, ?, {n,m}, greedy vs non-greedy |
| **Day 3** | Python re Module - Core Functions | search(), match(), findall(), sub() |
| **Day 4** | Match Objects, Regex Flags, Groups | Capturing groups, flags, span() |
| **Day 5** | Data Extraction, Parsing Files | Reading files, extracting patterns |
| **Day 6** | Data Validation, Input Sanitization | Email validation, security |
| **Day 7** | Lookahead/Lookbehind, Text Cleaning | Advanced patterns, optimization |
| **Day 8** | Performance Optimization, Best Practices | Greedy matching, debugging, alternatives |

---

## Introduction to Regular Expressions

A **Regular Expression (Regex)** is a sequence of characters defining a search pattern for:
- Text searching and matching
- Data validation (emails, phones, URLs)
- Find and replace operations
- Parsing structured data

---

## Day 1-2: Regex Fundamentals

### Special Characters

| Character | Name | Description | Example |
|-----------|------|-------------|---------|
| `.` | Dot | Matches any character except newline | `f.n` matches `fun`, `fan` |
| `^` | Caret | Start of string/line | `^Hello` matches string starting with "Hello" |
| `$` | Dollar | End of string/line | `world$` matches string ending with "world" |
| `\` | Backslash | Escapes special characters | `\.` matches literal dot |
| `[...]` | Character Class | Matches any character in brackets | `gr[ae]y` matches `gray`, `grey` |
| `[^...]` | Negated Set | Matches any character NOT in brackets | `[^abc]` matches any except a, b, c |
| `(...)` | Group | Groups patterns | `(ha)+` matches `ha`, `haha` |
| `|` | Alternation | OR operator | `abc|def` matches `abc` or `def` |

### Shorthand Character Classes

| Shorthand | Equivalent | Description |
|-----------|------------|-------------|
| `\d` | `[0-9]` | Any digit |
| `\D` | `[^0-9]` | Any non-digit |
| `\s` | `[ \t\n\r\f\v]` | Any whitespace |
| `\S` | `[^ \t\n\r\f\v]` | Any non-whitespace |
| `\w` | `[a-zA-Z0-9_]` | Any word character |
| `\W` | `[^a-zA-Z0-9_]` | Any non-word character |
| `\b` | - | Word boundary |

### Quantifiers

| Quantifier | Description | Example |
|------------|-------------|---------|
| `+` | One or more | `\d+` matches one or more digits |
| `*` | Zero or more | `\d*` matches zero or more digits |
| `?` | Zero or one (optional) | `colou?r` matches `color`, `colour` |
| `{n}` | Exactly n times | `\d{3}` matches exactly 3 digits |
| `{n,}` | At least n times | `\d{2,}` matches 2 or more digits |
| `{n,m}` | Between n and m times | `\d{2,4}` matches 2, 3, or 4 digits |

### Example: Hex Color Code

```python
import re

# Pattern for hex color: #ABC or #ABCDEF
pattern = r'^#((?:[a-fA-F0-9]){3}){1,2}$'

print(re.match(pattern, '#FFF'))      # Match
print(re.match(pattern, '#ABCDEF'))   # Match
print(re.match(pattern, '#GGG'))      # None
```

---

## Day 3-4: Python re Module

### Core Functions

```python
import re

text = "The price is $19.99, contact: email@example.com"

# 1. re.search() - Find first match
match = re.search(r'\$\d+\.\d{2}', text)
if match:
    print(match.group())  # $19.99

# 2. re.match() - Match at beginning only
match = re.match(r'The', text)
print(match.group() if match else "No match")  # The

# 3. re.fullmatch() - Match entire string
print(re.fullmatch(r'\d{3}', '123'))  # Match object
print(re.fullmatch(r'\d{3}', '1234'))  # None

# 4. re.findall() - Find all matches
numbers = re.findall(r'\d+', text)
print(numbers)  # ['19', '99']

# 5. re.sub() - Replace matches
new_text = re.sub(r'price', 'cost', text)
print(new_text)  # The cost is $19.99...

# 6. re.subn() - Replace and count
new_text, count = re.subn(r'\d+', 'X', text)
print(f"Replaced {count} times: {new_text}")

# 7. re.split() - Split by pattern
parts = re.split(r'[,:]', text)
print(parts)

# 8. re.compile() - Compile for reuse
pattern = re.compile(r'\d+')
print(pattern.findall(text))

# 9. re.escape() - Escape special characters
escaped = re.escape('$19.99')
print(escaped)  # \$19\.99
```

### Match Objects

```python
text = "Phone: 555-123-4567"
match = re.search(r'(\d{3})-(\d{3})-(\d{4})', text)

if match:
    print(match.group(0))   # Full match: 555-123-4567
    print(match.group(1))   # Group 1: 555
    print(match.group(2))   # Group 2: 123
    print(match.group(3))   # Group 3: 4567
    print(match.groups())   # All groups: ('555', '123', '4567')
    print(match.start())    # Start index
    print(match.end())      # End index
    print(match.span())     # (start, end) tuple
```

### Regex Flags

```python
# re.IGNORECASE (re.I) - Case-insensitive
print(re.search(r'hello', 'HELLO', re.I))  # Match

# re.MULTILINE (re.M) - ^ and $ match line boundaries
text = "Line 1\nLine 2\nLine 3"
print(re.findall(r'^Line', text, re.M))  # ['Line', 'Line', 'Line']

# re.DOTALL (re.S) - . matches newlines too
text = "Hello\nWorld"
print(re.search(r'Hello.World', text, re.S))  # Match

# Combining flags
pattern = re.compile(r'^hello', re.I | re.M)
```

---

## Day 5: Data Extraction and Parsing

### Reading Files and Finding Patterns

```python
import re

# Find errors in log file
try:
    with open('app.log', 'r') as file:
        for line_num, line in enumerate(file, 1):
            if re.search(r'error|exception', line, re.I):
                print(f"Line {line_num}: {line.strip()}")
except FileNotFoundError:
    print("File not found")
```

### Extracting Specific Data

```python
# Extract product codes (format: XX-NN-XX)
text = "Products: SK-45-B2, PRD-99-C3, ITEM-12-A1"
codes = re.findall(r'\b[A-Z]{2,4}-\d{2}-[A-Z]\d\b', text)
print(codes)  # ['SK-45-B2', 'PRD-99-C3', 'ITEM-12-A1']

# Extract email addresses
text = "Contact: john@example.com or support@company.org"
emails = re.findall(r'\b[\w.-]+@[\w.-]+\.\w{2,}\b', text)
print(emails)  # ['john@example.com', 'support@company.org']

# Extract URLs
text = "Visit https://example.com or http://test.org"
urls = re.findall(r'https?://[\w.-]+\.\w{2,}', text)
print(urls)  # ['https://example.com', 'http://test.org']

# Extract phone numbers
text = "Call 555-123-4567 or (555) 987-6543"
phones = re.findall(r'\(?\d{3}\)?[-.\s]?\d{3}[-.\s]?\d{4}', text)
print(phones)
```

### Non-Capturing Groups

```python
# Use (?:...) when you need grouping but not capturing
text = "Product: ABC-123-XYZ"

# Without non-capturing group
matches = re.findall(r'([A-Z]{3})-(\d{3})-([A-Z]{3})', text)
print(matches)  # [('ABC', '123', 'XYZ')]

# With non-capturing group
matches = re.findall(r'(?:[A-Z]{3})-(\d{3})-(?:[A-Z]{3})', text)
print(matches)  # ['123'] - Only middle group captured
```

---

## Day 6: Data Validation and Sanitization

### Validating User Input

```python
import re

def validate_username(username):
    """Username: 3-15 chars, starts with letter, alphanumeric + underscore"""
    pattern = r'^[a-zA-Z][\w-]{2,14}$'
    return bool(re.fullmatch(pattern, username))

print(validate_username("Alice123"))   # True
print(validate_username("123Alice"))   # False
print(validate_username("Al"))         # False

def validate_email(email):
    """Basic email validation"""
    pattern = r'^[\w.-]+@[\w.-]+\.\w{2,}$'
    return bool(re.fullmatch(pattern, email))

print(validate_email("user@example.com"))  # True
print(validate_email("invalid.email"))     # False

def validate_password(password):
    """Password: 8+ chars, 1 uppercase, 1 lowercase, 1 digit, 1 special"""
    if len(password) < 8:
        return False
    if not re.search(r'[A-Z]', password):
        return False
    if not re.search(r'[a-z]', password):
        return False
    if not re.search(r'\d', password):
        return False
    if not re.search(r'[!@#$%^&*(),.?":{}|<>]', password):
        return False
    return True

print(validate_password("Abc123!@"))  # True
print(validate_password("weak"))      # False

def validate_phone(phone):
    """US phone: (555) 123-4567 or 555-123-4567"""
    pattern = r'^\(?\d{3}\)?[-.\s]?\d{3}[-.\s]?\d{4}$'
    return bool(re.fullmatch(pattern, phone))

print(validate_phone("(555) 123-4567"))  # True
print(validate_phone("555-123-4567"))    # True
```

### Sanitizing Input (Security)

```python
def sanitize_input(data):
    """Remove potentially dangerous characters"""
    # Remove SQL injection characters
    return re.sub(r'[;\'\"()\<\>]', '', data)

user_input = "Robert'); DROP TABLE users;--"
clean = sanitize_input(user_input)
print(clean)  # Robert DROP TABLE users--

def sanitize_html(text):
    """Remove HTML tags"""
    return re.sub(r'<[^>]+>', '', text)

html = "<p>Hello <b>World</b>!</p>"
clean = sanitize_html(html)
print(clean)  # Hello World!

def sanitize_filename(filename):
    """Remove invalid filename characters"""
    return re.sub(r'[<>:"/\\|?*]', '_', filename)

filename = "report<2024>.txt"
clean = sanitize_filename(filename)
print(clean)  # report_2024_.txt
```

---

## Day 7-8: Advanced Patterns and Optimization

### Lookahead and Lookbehind

```python
import re

# Positive Lookahead (?=...)
# Match only if followed by pattern
text = "The price is $100 and amount is 200"
prices = re.findall(r'\d+(?=\s*dollars?)', "100 dollars and 200 euros")
print(prices)  # ['100']

# Positive Lookbehind (?<=...)
# Match only if preceded by pattern
prices = re.findall(r'(?<=\$)\d+', text)
print(prices)  # ['100']

# Negative Lookahead (?!...)
# Match only if NOT followed by pattern
words = re.findall(r'\b\w+(?!ing\b)', "running walking talk")
print(words)

# Negative Lookbehind (?<!...)
# Match only if NOT preceded by pattern
numbers = re.findall(r'(?<!\$)\d+', text)
print(numbers)  # ['200']
```

### Greedy vs Non-Greedy Matching

```python
text = "<p>First</p><p>Second</p>"

# Greedy (default) - matches as much as possible
greedy = re.search(r'<p>.*</p>', text)
print(greedy.group())  # <p>First</p><p>Second</p>

# Non-greedy (lazy) - matches as little as possible
lazy = re.search(r'<p>.*?</p>', text)
print(lazy.group())  # <p>First</p>

# Extract all paragraph contents
paragraphs = re.findall(r'<p>(.*?)</p>', text)
print(paragraphs)  # ['First', 'Second']
```

### Text Cleaning and Transformation

```python
# Remove punctuation
text = "Hello, World! How are you?"
clean = re.sub(r'[^\w\s]', '', text)
print(clean)  # Hello World How are you

# Standardize whitespace
text = "Too    many     spaces"
clean = re.sub(r'\s+', ' ', text)
print(clean)  # Too many spaces

# Extract hashtags
text = "Love #Python and #DataScience! #AI"
hashtags = re.findall(r'#\w+', text)
print(hashtags)  # ['#Python', '#DataScience', '#AI']

# Redact credit cards
text = "My card is 4111-2222-3333-4444"
redacted = re.sub(r'\b\d{4}-\d{4}-\d{4}-\d{4}\b', '[REDACTED]', text)
print(redacted)  # My card is [REDACTED]

# Redact emails
text = "Contact john@example.com for info"
redacted = re.sub(r'\b[\w.-]+@[\w.-]+\.\w+\b', '[EMAIL]', text)
print(redacted)  # Contact [EMAIL] for info
```

### Performance Optimization

```python
# 1. Compile patterns for reuse
pattern = re.compile(r'\d+')
for text in large_list:
    matches = pattern.findall(text)  # Faster than re.findall()

# 2. Use raw strings
pattern = r'\d+\.\d+'  # Good
# pattern = '\\d+\\.\\d+'  # Avoid

# 3. Be specific with quantifiers
# Slow: r'.*'
# Fast: r'\w+' or r'[a-zA-Z]+'

# 4. Use non-capturing groups when possible
# Slow: r'(\d{3})-(\d{3})-(\d{4})'
# Fast: r'(?:\d{3})-(?:\d{3})-(?:\d{4})'

# 5. Anchor patterns when possible
# Slow: r'test'
# Fast: r'^test' or r'test$'
```

### When to Use String Methods Instead

```python
text = "Hello, World!"

# Use string methods for simple cases (faster)
print(text.startswith('Hello'))  # Better than re.match(r'^Hello', text)
print(text.endswith('!'))        # Better than re.search(r'!$', text)
print('World' in text)           # Better than re.search(r'World', text)
print(text.replace('Hello', 'Hi'))  # Better than re.sub(r'Hello', 'Hi', text)

# Use regex for complex patterns
email_pattern = r'^[\w.-]+@[\w.-]+\.\w{2,}$'  # Regex needed
```

### Debugging with re.DEBUG

```python
# See how pattern is compiled
pattern = re.compile(r'\d{3}-\d{4}', re.DEBUG)
# Prints detailed compilation info
```

---

## 🎯 Practical Examples

### Example 1: Log File Parser

```python
import re

def parse_log_file(filename):
    """Extract errors, warnings, and timestamps from log"""
    pattern = r'(\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2})\s+\[(\w+)\]\s+(.*)'
    
    with open(filename, 'r') as file:
        for line in file:
            match = re.search(pattern, line)
            if match:
                timestamp, level, message = match.groups()
                if level in ['ERROR', 'WARNING']:
                    print(f"{timestamp} [{level}]: {message}")
```

### Example 2: Data Extraction from Text

```python
def extract_contact_info(text):
    """Extract emails and phones from text"""
    emails = re.findall(r'\b[\w.-]+@[\w.-]+\.\w{2,}\b', text)
    phones = re.findall(r'\(?\d{3}\)?[-.\s]?\d{3}[-.\s]?\d{4}', text)
    
    return {
        'emails': emails,
        'phones': phones
    }

text = """
Contact us:
Email: support@company.com
Phone: (555) 123-4567
Alt: info@company.org or 555-987-6543
"""

info = extract_contact_info(text)
print(info)
```

### Example 3: Password Strength Checker

```python
def check_password_strength(password):
    """Check password strength and provide feedback"""
    feedback = []
    score = 0
    
    if len(password) >= 8:
        score += 1
    else:
        feedback.append("At least 8 characters required")
    
    if re.search(r'[A-Z]', password):
        score += 1
    else:
        feedback.append("Add uppercase letters")
    
    if re.search(r'[a-z]', password):
        score += 1
    else:
        feedback.append("Add lowercase letters")
    
    if re.search(r'\d', password):
        score += 1
    else:
        feedback.append("Add numbers")
    
    if re.search(r'[!@#$%^&*(),.?":{}|<>]', password):
        score += 1
    else:
        feedback.append("Add special characters")
    
    strength = ['Very Weak', 'Weak', 'Fair', 'Good', 'Strong'][score-1] if score > 0 else 'Very Weak'
    
    return {
        'strength': strength,
        'score': score,
        'feedback': feedback
    }

result = check_password_strength("Abc123!@")
print(result)
```

---

## 📚 Quick Reference

### Common Patterns

```python
# Email
r'^[\w.-]+@[\w.-]+\.\w{2,}$'

# URL
r'https?://[\w.-]+\.\w{2,}(?:/[\w.-]*)*'

# Phone (US)
r'\(?\d{3}\)?[-.\s]?\d{3}[-.\s]?\d{4}'

# Date (YYYY-MM-DD)
r'\d{4}-\d{2}-\d{2}'

# Time (HH:MM:SS)
r'\d{2}:\d{2}:\d{2}'

# IP Address
r'\b(?:\d{1,3}\.){3}\d{1,3}\b'

# Hex Color
r'#[a-fA-F0-9]{6}|#[a-fA-F0-9]{3}'

# Credit Card
r'\b\d{4}[-\s]?\d{4}[-\s]?\d{4}[-\s]?\d{4}\b'

# Username (3-16 chars, alphanumeric + underscore)
r'^[a-zA-Z0-9_]{3,16}$'

# Strong Password
r'^(?=.*[a-z])(?=.*[A-Z])(?=.*\d)(?=.*[@$!%*?&])[A-Za-z\d@$!%*?&]{8,}$'
```

---

## 🚀 Best Practices

1. **Use raw strings**: Always use `r''` for regex patterns
2. **Compile patterns**: Use `re.compile()` for repeated use
3. **Be specific**: Avoid overly broad patterns like `.*`
4. **Test thoroughly**: Use online tools like regex101.com
5. **Comment complex patterns**: Explain what pattern does
6. **Consider alternatives**: Use string methods for simple cases
7. **Validate carefully**: Don't rely solely on regex for security
8. **Handle errors**: Use try-except for user input validation

**Happy Pattern Matching! 🎯**
