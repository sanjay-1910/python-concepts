# Popular List Methods in Python

A list is an ordered, mutable collection that allows duplicate elements. Since lists are mutable, you can modify them after creation.

Example:

```python
numbers = [1, 2, 3, 4]

```

----------

## 1. Adding Elements

### append()

Adds a single element to the end of the list.

```python
fruits = ["apple", "banana"]
fruits.append("mango")

print(fruits)   # ['apple', 'banana', 'mango']

```

----------

### extend()

Adds multiple elements from another iterable (list, tuple, set).

```python
numbers = [1, 2]
numbers.extend([3, 4, 5])

print(numbers)   # [1, 2, 3, 4, 5]

```

Difference between append and extend:

```python
a = [1, 2]
a.append([3, 4])    # Adds as a single element
print(a)           # [1, 2, [3, 4]]

b = [1, 2]
b.extend([3, 4])   # Adds individually
print(b)           # [1, 2, 3, 4]

```

----------

### insert()

Inserts an element at a specific position.

```python
numbers = [1, 3, 4]
numbers.insert(1, 2)

print(numbers)   # [1, 2, 3, 4]

```

----------

## 2. Removing Elements

### remove()

Removes the first occurrence of a specified value.

```python
numbers = [1, 2, 3, 2]
numbers.remove(2)

print(numbers)   # [1, 3, 2]

```

Raises an error if the element is not found.

----------

### pop()

Removes and returns the element at the given index. Default removes the last element.

```python
numbers = [10, 20, 30]
numbers.pop()

print(numbers)   # [10, 20]

```

Using index:

```python
numbers.pop(0)
print(numbers)   # [20]

```

----------

### clear()

Removes all elements from the list.

```python
numbers = [1, 2, 3]
numbers.clear()

print(numbers)   # []

```

----------

### del (keyword)

Deletes elements using index or removes the entire list.

```python
numbers = [1, 2, 3, 4]
del numbers[1]

print(numbers)   # [1, 3, 4]

```

----------

## 3. Searching and Counting

### index()

Returns the index of the first occurrence of a value.

```python
numbers = [10, 20, 30]
print(numbers.index(20))   # 1

```

Raises an error if not found.

----------

### count()

Counts how many times an element appears.

```python
numbers = [1, 2, 2, 3, 2]
print(numbers.count(2))   # 3

```

----------

## 4. Sorting and Reversing

### sort()

Sorts the list in ascending order by default.

```python
numbers = [4, 1, 3, 2]
numbers.sort()

print(numbers)   # [1, 2, 3, 4]

```

Descending order:

```python
numbers.sort(reverse=True)

```

Sorting strings:

```python
names = ["Sanjay", "Anil", "Vijay"]
names.sort()

```

----------

### sorted()

Returns a new sorted list without modifying the original.

```python
numbers = [3, 1, 2]
new_list = sorted(numbers)

print(new_list)   # [1, 2, 3]
print(numbers)    # Original unchanged

```

----------

### reverse()

Reverses the list in place.

```python
numbers = [1, 2, 3]
numbers.reverse()

print(numbers)   # [3, 2, 1]

```

----------

## 5. Copying Lists

### copy()

Creates a shallow copy of the list.

```python
original = [1, 2, 3]
duplicate = original.copy()

duplicate.append(4)

print(original)   # [1, 2, 3]
print(duplicate)  # [1, 2, 3, 4]

```

----------

### list()

Another way to create a copy.

```python
a = [1, 2, 3]
b = list(a)

```

----------

## 6. Useful Built-in Functions for Lists

### len()

Returns the number of elements.

```python
numbers = [1, 2, 3]
print(len(numbers))   # 3

```

----------

### max() and min()

Return the largest and smallest elements.

```python
numbers = [4, 2, 9, 1]
print(max(numbers))   # 9
print(min(numbers))   # 1

```

----------

### sum()

Returns the total of all elements.

```python
numbers = [1, 2, 3, 4]
print(sum(numbers))   # 10

```

----------

## 7. List Slicing

Access parts of a list using slicing.

Syntax:

```
list[start : end : step]

```

Example:

```python
numbers = [0, 1, 2, 3, 4, 5]

print(numbers[1:4])   # [1, 2, 3]
print(numbers[:3])    # [0, 1, 2]
print(numbers[::2])   # [0, 2, 4]
print(numbers[::-1])  # Reverse list

```

----------

## 8. List Comprehension

A shorter way to create lists.

```python
squares = [x**2 for x in range(5)]
print(squares)   # [0, 1, 4, 9, 16]

```

With condition:

```python
evens = [x for x in range(10) if x % 2 == 0]

```

----------

## 9. Checking Membership

```python
numbers = [1, 2, 3]

print(2 in numbers)      # True
print(5 not in numbers)  # True

```

----------

## 10. Iterating Through a List

```python
fruits = ["apple", "banana", "mango"]

for fruit in fruits:
    print(fruit)

```

Using index:

```python
for i in range(len(fruits)):
    print(fruits[i])

```


## Summary

-   Lists are ordered and mutable collections.
    
-   Use `append()`, `extend()`, and `insert()` to add elements.
    
-   Use `remove()`, `pop()`, and `clear()` to delete elements.
    
-   `sort()` modifies the list, while `sorted()` returns a new list.
    
-   `copy()` prevents unwanted changes to the original list.
    
-   List comprehension provides a concise way to create lists.

-   Lists are ordered and mutable collections.
    
-   Use `append()`, `extend()`, and `insert()` to add elements.
    
-   Use `remove()`, `pop()`, and `clear()` to delete elements.
    
-   `sort()` modifies the list, while `sorted()` returns a new list.
    
-   `copy()` prevents unwanted changes to the original list.
    
-   List comprehension provides a concise way to create lists.