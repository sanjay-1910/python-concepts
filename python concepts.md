
# Python Basic Concepts Cheat Sheet

## 1. Introduction to Python
Python is a high-level, interpreted programming language that focuses on readability and simplicity. It is widely used in web development, automation, data science, machine learning, and software development.

Example:

```python
print("Hello, Python!")

```

----------

## 2. Features of Python

-   Easy to learn and use
    
-   Interpreted language (no need for compilation)
    
-   Dynamically typed (no need to declare variable types)
    
-   Large standard library
    
-   Supports multiple programming paradigms such as procedural, object-oriented, and functional programming
    
-   Portable across different operating systems
    

----------

## 3. Variables

Variables are containers used to store data values. Python automatically determines the type of data stored.

Rules for naming variables:

-   Must start with a letter or underscore
    
-   Cannot start with a number
    
-   Cannot use reserved keywords
    
-   Case-sensitive (age and Age are different)
    

Example:

```python
name = "Sanjay"
age = 21
percentage = 85.5
is_student = True

```

Multiple assignment:

```python
a, b, c = 1, 2, 3

```

----------

## 4. Data Types

### Numeric Types

Used to store numbers.

```python
x = 10        # int
y = 3.14      # float
z = 2 + 5j    # complex

```

### String

A string is a sequence of characters enclosed in quotes.

```python
message = "Python is simple"

```

### Boolean

Represents either True or False.

```python
is_logged_in = False

```

### List

An ordered and mutable collection that allows duplicates.

```python
fruits = ["apple", "banana", "mango"]
fruits.append("orange")

```

### Tuple

An ordered but immutable collection.

```python
coordinates = (10, 20)

```

### Set

An unordered collection that does not allow duplicate values.

```python
numbers = {1, 2, 3, 4}

```

### Dictionary

Stores data as key-value pairs.

```python
student = {
    "name": "Sanjay",
    "age": 21,
    "branch": "CSE"
}

```

Check data type:

```python
print(type(student))

```

----------

## 5. Type Casting

Type casting means converting one data type into another.

```python
age = "21"
age = int(age)

price = 100
price_str = str(price)

num = 5
num_float = float(num)

```

----------

## 6. Taking User Input

The `input()` function is used to accept user input. It always returns a string.

```python
name = input("Enter your name: ")
age = int(input("Enter your age: "))

```

----------

## 7. Operators

### Arithmetic Operators

```python
a = 10
b = 3

print(a + b)   # Addition
print(a - b)   # Subtraction
print(a * b)   # Multiplication
print(a / b)   # Division
print(a % b)   # Modulus
print(a ** b)  # Exponentiation
print(a // b)  # Floor division

```

### Comparison Operators

```python
print(10 > 5)
print(10 == 5)
print(10 != 5)
print(10 >= 5)

```

### Logical Operators

```python
print(True and False)
print(True or False)
print(not True)

```

### Assignment Operators

```python
x = 5
x += 2
x -= 1
x *= 3

```

----------

## 8. Conditional Statements

Conditional statements allow a program to make decisions based on conditions.

### if Statement

```python
age = 18

if age >= 18:
    print("Eligible to vote")

```

### if-else Statement

```python
number = 7

if number % 2 == 0:
    print("Even")
else:
    print("Odd")

```

### if-elif-else Ladder

```python
marks = 82

if marks >= 90:
    print("Grade A")
elif marks >= 75:
    print("Grade B")
elif marks >= 50:
    print("Grade C")
else:
    print("Fail")

```

### Nested if

```python
age = 20
has_id = True

if age >= 18:
    if has_id:
        print("Entry allowed")

```

----------

## 9. Loops

Loops are used to execute a block of code multiple times.

### for Loop

Used when the number of iterations is known.

```python
for i in range(5):
    print(i)

```

Iterating through a list:

```python
fruits = ["apple", "banana", "mango"]

for fruit in fruits:
    print(fruit)

```

### while Loop

Executes as long as the condition is True.

```python
count = 1

while count <= 5:
    print(count)
    count += 1

```

----------

## 10. Loop Control Statements

### break

Terminates the loop immediately.

```python
for i in range(10):
    if i == 5:
        break
    print(i)

```

### continue

Skips the current iteration.

```python
for i in range(5):
    if i == 2:
        continue
    print(i)

```

### pass

Acts as a placeholder when a statement is required syntactically but no action is needed.

```python
for i in range(5):
    pass

```

----------

## 11. Functions

Functions are reusable blocks of code that perform a specific task.

```python
def greet(name):
    return f"Hello, {name}"

print(greet("Sanjay"))

```

Default parameter:

```python
def greet(name="User"):
    print("Hello", name)

```

----------

## 12. Indentation

Python uses indentation instead of braces to define code blocks. Incorrect indentation will cause errors.

Correct:

```python
if True:
    print("Hello")

```

Incorrect:

```python
if True:
print("Hello")

```

----------

## 13. Comments

Comments are used to explain code and improve readability.

Single-line comment:

```python
# This is a comment

```

Multi-line comment:

```python
"""
This is a multi-line comment
"""

```

----------

## 14. Membership Operators

Used to check whether a value exists in a sequence.

```python
fruits = ["apple", "banana"]

print("apple" in fruits)
print("grape" not in fruits)

```

----------

## 15. Identity Operators

Used to check whether two variables refer to the same memory location.

```python
a = [1, 2, 3]
b = a

print(a is b)
print(a is not b)

```

----------

## 16. Mutable vs Immutable

Mutable objects can be modified after creation:

-   List
    
-   Dictionary
    
-   Set
    

Immutable objects cannot be changed:

-   int
    
-   float
    
-   string
    
-   tuple
    

Example:

```python
# Mutable
numbers = [1, 2, 3]
numbers.append(4)

# Immutable
text = "hello"
# text[0] = "H"  -> Error

```

----------

## 17. Python Keywords

Keywords are reserved words that cannot be used as variable names.

Examples include:

```
False, True, None, and, or, not, if, else, elif, for, while, break,
continue, pass, def, return, class, try, except, finally, lambda

```

----------

## Summary

-   Python is simple, readable, and powerful.
    
-   Variables store data without explicit type declaration.
    
-   Data types define the kind of value stored.
    
-   Operators perform operations on data.
    
-   Conditionals help in decision-making.
    
-   Loops automate repetitive tasks.
    
-   Functions improve code reusability.
    
-   Proper indentation is mandatory in Python.