# Object Oriented Programming (OOP) in Python

## What is Object Oriented Programming?

Object Oriented Programming (OOP) is a programming paradigm that organizes code into **objects**, which are instances of **classes**. It helps structure programs in a way that is reusable, scalable, and easy to maintain.

OOP focuses on modeling real-world entities using objects that contain both **data (attributes)** and **behavior (methods)**.

---

## Why Use OOP?

- Promotes code reusability
- Makes programs easier to manage
- Improves readability
- Enhances security through data hiding
- Allows scalability for large applications

---

## Basic Terminologies

### Class
A class is a blueprint or template used to create objects.

Example:

```python
class Student:
    pass

```

----------

### Object

An object is an instance of a class. It represents a real-world entity.

```python
class Student:
    pass

s1 = Student()
print(type(s1))

```

----------

## Creating a Class with Attributes and Methods

```python
class Student:

    # Constructor
    def __init__(self, name, age):
        self.name = name
        self.age = age

    # Method
    def display(self):
        print(f"Name: {self.name}, Age: {self.age}")


# Creating object
s1 = Student("Sanjay", 21)
s1.display()

```

### Explanation:

-   `__init__` is a constructor that runs automatically when an object is created.
    
-   `self` refers to the current object.
    
-   Attributes store object data.
    
-   Methods define object behavior.
    

----------

## The self Keyword

`self` represents the instance of the class and allows access to its variables and methods.

```python
class Car:

    def __init__(self, brand):
        self.brand = brand

    def show(self):
        print("Car brand is", self.brand)

c1 = Car("Toyota")
c1.show()

```

----------

## Types of Variables in OOP

### Instance Variables

Belong to a specific object.

```python
class Student:
    def __init__(self, name):
        self.name = name   # Instance variable

```

Each object can have different values.

----------

### Class Variables

Shared among all objects.

```python
class College:
    college_name = "AEC"   # Class variable

    def __init__(self, student):
        self.student = student

print(College.college_name)

```

----------

## Types of Methods

### Instance Methods

Operate on instance variables.

```python
class Dog:
    def __init__(self, name):
        self.name = name

    def bark(self):
        print(self.name, "is barking")

```

----------

### Class Methods

Operate on class variables using `cls`.

```python
class College:
    name = "AEC"

    @classmethod
    def change_name(cls, new_name):
        cls.name = new_name

College.change_name("Aditya Engineering College")
print(College.name)

```

----------

### Static Methods

Do not depend on class or instance data.

```python
class MathUtils:

    @staticmethod
    def add(a, b):
        return a + b

print(MathUtils.add(2, 3))

```

----------

## Constructor

A constructor is a special method used to initialize object attributes.

```python
class Person:

    def __init__(self, name):
        self.name = name

p1 = Person("Sanjay")

```

Python does not support multiple constructors directly, but default arguments can be used.

----------

## Four Pillars of OOP

1.  Encapsulation
    
2.  Abstraction
    
3.  Inheritance
    
4.  Polymorphism
    

----------

# 1. Encapsulation

Encapsulation means bundling data and methods together and restricting direct access to some components.

### Access Modifiers in Python

-   Public
    
-   Protected
    
-   Private
    

----------

### Public Members

Accessible from anywhere.

```python
class Employee:
    def __init__(self):
        self.name = "Sanjay"

emp = Employee()
print(emp.name)

```

----------

### Protected Members (Single underscore `_`)

Indicates internal use (convention).

```python
class Employee:
    def __init__(self):
        self._salary = 50000

```

----------

### Private Members (Double underscore `__`)

Name mangling prevents direct access.

```python
class Employee:
    def __init__(self):
        self.__salary = 50000

    def get_salary(self):
        return self.__salary

emp = Employee()
print(emp.get_salary())

```

----------

# 2. Abstraction

Abstraction hides implementation details and shows only essential features.

Python achieves abstraction using **abstract classes**.

```python
from abc import ABC, abstractmethod

class Shape(ABC):

    @abstractmethod
    def area(self):
        pass


class Circle(Shape):

    def __init__(self, radius):
        self.radius = radius

    def area(self):
        return 3.14 * self.radius * self.radius


c = Circle(5)
print(c.area())

```

Cannot create objects of an abstract class.

----------

# 3. Inheritance

Inheritance allows one class to acquire properties of another.

### Parent → Base class

### Child → Derived class

----------

## Single Inheritance

```python
class Animal:
    def eat(self):
        print("Eating")


class Dog(Animal):
    def bark(self):
        print("Barking")

d = Dog()
d.eat()
d.bark()

```

----------

## Multiple Inheritance

```python
class Father:
    def skills(self):
        print("Gardening")


class Mother:
    def skills(self):
        print("Cooking")


class Child(Father, Mother):
    pass

c = Child()
c.skills()

```

Python follows **Method Resolution Order (MRO)**.

----------

## Multilevel Inheritance

```python
class Grandparent:
    def house(self):
        print("Owns a house")


class Parent(Grandparent):
    pass


class Child(Parent):
    pass

child = Child()
child.house()

```

----------

## Hierarchical Inheritance

```python
class Animal:
    def speak(self):
        print("Speaking")


class Dog(Animal):
    pass


class Cat(Animal):
    pass

```

----------

# 4. Polymorphism

Polymorphism means "many forms". The same method name behaves differently depending on the object.

----------

## Method Overriding

Child class provides a new implementation of a parent method.

```python
class Animal:
    def sound(self):
        print("Animal makes a sound")


class Dog(Animal):
    def sound(self):
        print("Dog barks")

d = Dog()
d.sound()

```

----------

## Operator Overloading

Python allows operators to behave differently for objects.

```python
print(5 + 3)          # 8
print("Hello " + "World")   # Concatenation

```

Custom example:

```python
class Point:

    def __init__(self, x):
        self.x = x

    def __add__(self, other):
        return self.x + other.x

p1 = Point(10)
p2 = Point(20)

print(p1 + p2)

```

----------

## Duck Typing

Python focuses on behavior rather than type.

"If it looks like a duck and behaves like a duck, it is a duck."

```python
class Bird:
    def fly(self):
        print("Flying")

class Airplane:
    def fly(self):
        print("Airplane flying")

for obj in [Bird(), Airplane()]:
    obj.fly()

```

----------

## Special (Magic / Dunder) Methods

Common special methods:

-   `__init__` → Constructor
    
-   `__str__` → String representation
    
-   `__len__` → Length
    
-   `__add__` → Addition
    

Example:

```python
class Book:

    def __init__(self, pages):
        self.pages = pages

    def __str__(self):
        return f"Book with {self.pages} pages"

b = Book(200)
print(b)

```

----------

## Composition (Has-A Relationship)

Instead of inheriting, a class can contain another class.

```python
class Engine:
    def start(self):
        print("Engine started")


class Car:
    def __init__(self):
        self.engine = Engine()

car = Car()
car.engine.start()

```

----------

## Advantages of OOP

-   Code reusability through inheritance
    
-   Better organization
    
-   Easier debugging
    
-   Improved scalability
    
-   Data security using encapsulation
    


## Summary

-   OOP organizes code using classes and objects.
    
-   Encapsulation protects data.
    
-   Abstraction hides complexity.
    
-   Inheritance promotes reuse.
    
-   Polymorphism allows flexibility.
    
-   Python fully supports OOP, making it ideal for building scalable applications.