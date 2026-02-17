# Python Dictionary Cheat Sheet

## What is a Dictionary?

A dictionary is a built-in data type in Python used to store data in **key-value pairs**.

- Keys must be unique.
- Keys must be immutable (string, number, tuple).
- Values can be of any data type.
- Dictionaries are mutable (can be modified after creation).
- They are unordered (before Python 3.7) and insertion-ordered (Python 3.7+).

---

## Creating a Dictionary

### Using Curly Braces

```python
student = {
    "name": "Sanjay",
    "age": 21,
    "branch": "CSE"
}

print(student)

```

### Using dict() Constructor

```python
student = dict(name="Sanjay", age=21, branch="CSE")

```

### Empty Dictionary

```python
data = {}
# or
data = dict()

```

----------

## Accessing Values

### Using Keys

```python
student = {"name": "Sanjay", "age": 21}

print(student["name"])

```

If the key does not exist, it raises an error.

----------

### Using get() (Safer Method)

```python
print(student.get("age"))
print(student.get("marks", "Not Found"))

```

Does not raise an error if the key is missing.

----------

## Adding and Updating Elements

### Add a New Key

```python
student["college"] = "AEC"

```

### Update Existing Value

```python
student["age"] = 22

```

### Using update()

```python
student.update({"age": 23, "city": "Kakinada"})

```

----------

## Removing Elements

### pop()

Removes the specified key and returns its value.

```python
student = {"name": "Sanjay", "age": 21}

student.pop("age")
print(student)

```

----------

### popitem()

Removes the last inserted key-value pair.

```python
student.popitem()

```

----------

### del Keyword

```python
del student["name"]

```

Delete entire dictionary:

```python
del student

```

----------

### clear()

Removes all elements.

```python
student.clear()

```

----------

## Important Dictionary Methods

### keys()

Returns all keys.

```python
student = {"name": "Sanjay", "age": 21}

print(student.keys())

```

----------

### values()

Returns all values.

```python
print(student.values())

```

----------

### items()

Returns key-value pairs as tuples.

```python
print(student.items())

```

----------

### copy()

Creates a shallow copy of the dictionary.

```python
new_student = student.copy()

```

----------

### fromkeys()

Creates a dictionary with specified keys and a common value.

```python
keys = ["a", "b", "c"]

new_dict = dict.fromkeys(keys, 0)
print(new_dict)

```

----------

### setdefault()

Returns the value of a key. If the key does not exist, it inserts the key with a specified value.

```python
student = {"name": "Sanjay"}

student.setdefault("age", 21)
print(student)

```

----------

## Dictionary Operations

### Check if Key Exists

```python
student = {"name": "Sanjay"}

print("name" in student)
print("age" not in student)

```

----------

### Find Length

```python
print(len(student))

```

----------

### Loop Through Dictionary

#### Loop Through Keys

```python
for key in student:
    print(key)

```

----------

#### Loop Through Values

```python
for value in student.values():
    print(value)

```

----------

#### Loop Through Key-Value Pairs

```python
for key, value in student.items():
    print(key, value)

```

----------

## Nested Dictionaries

A dictionary can contain another dictionary.

```python
students = {
    "student1": {"name": "Sanjay", "age": 21},
    "student2": {"name": "Rahul", "age": 22}
}

print(students["student1"]["name"])

```

----------

## Dictionary Comprehension

A concise way to create dictionaries.

```python
squares = {x: x*x for x in range(5)}
print(squares)

```

With condition:

```python
even_squares = {x: x*x for x in range(10) if x % 2 == 0}

```

----------

## Mutable vs Immutable Keys

Allowed as keys:

-   Strings
    
-   Numbers
    
-   Tuples (only if they contain immutable elements)
    

Not allowed:

-   Lists
    
-   Sets
    
-   Other dictionaries
    

Example:

```python
data = {(1, 2): "valid"}   # Allowed

```

----------

## Advantages (Features) of Dictionaries

-   Fast lookup using keys (O(1) average time complexity)
    
-   Dynamic size (can grow and shrink)
    
-   Stores data in key-value format
    
-   Easy to modify
    
-   Supports nested structures
    
-   Ideal for mapping relationships
    

----------

## Common Built-in Functions

### len()

```python
print(len(student))

```

### type()

```python
print(type(student))

```

### sorted()

```python
data = {"b": 2, "a": 1, "c": 3}

print(sorted(data))   # Sorts keys

```

----------

## Difference Between get() and []

get()

[]

Returns None if key missing

Raises KeyError

Safer

Faster

Can provide default value

Cannot

----------

## Important Notes

-   Keys must be unique.
    
-   Dictionaries are mutable.
    
-   Assignment does not create a copy.
    

Example:

```python
a = {"x": 1}
b = a

b["x"] = 100

print(a)   # {'x': 100}

```

----------

## Summary

-   Dictionaries store data as key-value pairs.
    
-   Use `get()` for safe access.
    
-   `update()` adds or modifies elements.
    
-   `pop()` and `del` remove elements.
    
-   `keys()`, `values()`, and `items()` help in traversal.
    
-   Dictionary comprehension makes creation faster.
    
-   Best data structure for fast lookups and mappings.