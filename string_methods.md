
# Popular String Methods in Python

Strings are immutable sequences of characters in Python. Once created, they cannot be changed, but string methods return new strings after performing operations.

---

## 1. Changing Case

### lower()
Converts all characters to lowercase.

```python
text = "HELLO"
print(text.lower())     # hello

```

### upper()

Converts all characters to uppercase.

```python
text = "python"
print(text.upper())     # PYTHON

```

### title()

Capitalizes the first letter of every word.

```python
text = "welcome to python"
print(text.title())     # Welcome To Python

```

### capitalize()

Capitalizes only the first character of the string.

```python
text = "hello world"
print(text.capitalize())   # Hello world

```

### swapcase()

Swaps lowercase letters to uppercase and vice versa.

```python
text = "PyThOn"
print(text.swapcase())     # pYtHoN

```

----------

## 2. Searching and Finding

### find()

Returns the index of the first occurrence of a substring. Returns -1 if not found.

```python
text = "python programming"
print(text.find("program"))   # 7

```

### rfind()

Finds the last occurrence of a substring.

```python
text = "apple banana apple"
print(text.rfind("apple"))    # 13

```

### index()

Similar to `find()` but raises an error if the substring is not found.

```python
text = "hello"
print(text.index("e"))    # 1

```

### count()

Counts how many times a substring appears.

```python
text = "banana"
print(text.count("a"))    # 3

```

### startswith()

Checks if a string starts with a given prefix.

```python
text = "Python is easy"
print(text.startswith("Python"))   # True

```

### endswith()

Checks if a string ends with a given suffix.

```python
text = "file.txt"
print(text.endswith(".txt"))   # True

```

----------

## 3. Replacing and Modifying

### replace()

Replaces occurrences of a substring with another substring.

```python
text = "I like Java"
print(text.replace("Java", "Python"))

```

You can also limit replacements:

```python
text = "one one one"
print(text.replace("one", "two", 2))   # two two one

```

### strip()

Removes whitespace from both sides of a string.

```python
text = "   hello   "
print(text.strip())     # "hello"

```

### lstrip()

Removes whitespace from the left side.

```python
text = "   hello"
print(text.lstrip())

```

### rstrip()

Removes whitespace from the right side.

```python
text = "hello   "
print(text.rstrip())

```

----------

## 4. Splitting and Joining

### split()

Splits a string into a list based on a separator. Default separator is space.

```python
text = "apple banana mango"
print(text.split())

```

Using a custom separator:

```python
data = "a,b,c"
print(data.split(","))

```

### rsplit()

Splits from the right side.

```python
text = "one-two-three"
print(text.rsplit("-", 1))   # ['one-two', 'three']

```

### join()

Joins elements of a list into a single string.

```python
words = ["Python", "is", "fun"]
result = " ".join(words)
print(result)     # Python is fun

```

----------

## 5. Checking String Properties

### isalpha()

Returns True if all characters are alphabets.

```python
text = "Python"
print(text.isalpha())   # True

```

### isdigit()

Returns True if all characters are digits.

```python
text = "12345"
print(text.isdigit())   # True

```

### isalnum()

Checks whether the string is alphanumeric (letters and numbers).

```python
text = "Python123"
print(text.isalnum())   # True

```

### islower()

Checks if all characters are lowercase.

```python
text = "hello"
print(text.islower())

```

### isupper()

Checks if all characters are uppercase.

```python
text = "HELLO"
print(text.isupper())

```

### isspace()

Returns True if the string contains only whitespace.

```python
text = "   "
print(text.isspace())

```

### istitle()

Checks if the string is in title case.

```python
text = "Hello World"
print(text.istitle())

```

----------

## 6. Alignment Methods

### center()

Centers the string within a specified width.

```python
text = "Python"
print(text.center(10, "-"))   # --Python--

```

### ljust()

Left-aligns the string.

```python
text = "Hi"
print(text.ljust(5, "*"))   # Hi***

```

### rjust()

Right-aligns the string.

```python
text = "Hi"
print(text.rjust(5, "*"))   # ***Hi

```

### zfill()

Pads the string with zeros on the left.

```python
num = "42"
print(num.zfill(5))    # 00042

```

----------

## 7. Partitioning

### partition()

Splits the string into three parts: before separator, separator, after separator.

```python
text = "user@email.com"
print(text.partition("@"))

```

### rpartition()

Splits from the right.

```python
text = "one-two-three"
print(text.rpartition("-"))

```

----------

## 8. Formatting Strings

### format()

Formats values inside a string.

```python
name = "Sanjay"
age = 21

print("My name is {} and I am {} years old".format(name, age))

```

### f-strings (Recommended)

Cleaner and faster formatting.

```python
name = "Sanjay"
print(f"Hello, {name}")

```

----------

## 9. Encoding and Decoding

### encode()

Converts a string into bytes.

```python
text = "hello"
encoded = text.encode("utf-8")
print(encoded)

```

### decode()

Converts bytes back into a string.

```python
print(encoded.decode("utf-8"))

```

----------

## 10. Useful Additional Methods

### len()

Returns the length of a string.

```python
text = "Python"
print(len(text))   # 6

```

### sorted()

Returns a sorted list of characters.

```python
text = "python"
print(sorted(text))

```

### reversed()

Reverses the string.

```python
text = "hello"
print("".join(reversed(text)))

```

Slicing method (commonly used):

```python
text = "hello"
print(text[::-1])   # olleh

```

----------

## Summary

-   Strings are immutable in Python.
    
-   Methods like `lower()`, `upper()`, and `replace()` help modify strings.
    
-   Searching methods include `find()`, `index()`, and `count()`.
    
-   Use `split()` to break strings and `join()` to combine them.
    
-   Validation methods such as `isalpha()` and `isdigit()` help check string content.
    
-   Formatting can be done using `format()` or f-strings.