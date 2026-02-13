
# Types of Copy in Python (Shallow Copy vs Deep Copy)

When working with lists, dictionaries, or other mutable objects, copying is important to avoid modifying the original data unintentionally.

There are two main types of copying in Python:

1. Shallow Copy  
2. Deep Copy  

---

## 1. Shallow Copy

A shallow copy creates a new object, but it does **not copy nested objects**.  
Instead, it copies the references of those nested objects.

This means:
- Changes to the outer object do NOT affect the original.
- Changes to nested objects WILL affect the original.

---

### Example of Shallow Copy

```python
import copy

original = [[1, 2], [3, 4]]

shallow_copy = copy.copy(original)

shallow_copy[0][0] = 100

print("Original:", original)
print("Shallow Copy:", shallow_copy)

```

Output:

```
Original: [[100, 2], [3, 4]]
Shallow Copy: [[100, 2], [3, 4]]

```

Both changed because the inner lists are shared.

----------

### Ways to Create a Shallow Copy

#### Using copy()

```python
import copy

a = [1, 2, 3]
b = copy.copy(a)

```

#### Using list.copy()

```python
a = [1, 2, 3]
b = a.copy()

```

#### Using slicing

```python
a = [1, 2, 3]
b = a[:]

```

----------

### When to Use Shallow Copy

Use shallow copy when:

-   Your list contains only primitive data types (int, float, string).
    
-   You do not have nested mutable objects.
    

----------

## 2. Deep Copy

A deep copy creates a completely independent copy of the original object, including all nested objects.

This means:

-   Changes in the copied object will NOT affect the original.
    
-   Fully separate memory is allocated.
    

----------

### Example of Deep Copy

```python
import copy

original = [[1, 2], [3, 4]]

deep_copy = copy.deepcopy(original)

deep_copy[0][0] = 100

print("Original:", original)
print("Deep Copy:", deep_copy)

```

Output:

```
Original: [[1, 2], [3, 4]]
Deep Copy: [[100, 2], [3, 4]]

```

Now the original list remains unchanged.

----------

### How Deep Copy Works

-   Recursively copies every object.
    
-   No shared references.
    
-   Completely independent structure.
    


## Visual Understanding

```
Shallow Copy:
Original -> Inner List A
Copy ------^

Deep Copy:
Original -> Inner List A
Copy -> Inner List B

```

----------

## When Should You Use Deep Copy?

Use deep copy when:

-   Working with nested lists or dictionaries
    
-   Modifying data structures independently
    
-   Avoiding unexpected side effects
    
-   Handling complex objects
    

----------

## Important Note

Assignment is NOT copying.

```python
a = [1, 2, 3]
b = a

b[0] = 100

print(a)   # [100, 2, 3]

```

Both variables refer to the same object in memory.

----------

## Summary

-   Shallow copy duplicates only the outer object.
    
-   Deep copy duplicates the entire structure.
    
-   Use shallow copy for simple data.
    
-   Use deep copy for nested mutable objects.
    
-   Always be careful when copying lists or dictionaries to avoid unintended modifications.