
# SOLID Principles in Python

## What is SOLID?

SOLID is a set of five design principles used in Object Oriented Programming to make software more **understandable, flexible, maintainable, and scalable**.

The term SOLID stands for:

- S → Single Responsibility Principle  
- O → Open/Closed Principle  
- L → Liskov Substitution Principle  
- I → Interface Segregation Principle  
- D → Dependency Inversion Principle  

Following these principles helps developers write clean and professional code.


# 1. Single Responsibility Principle (SRP)

## Definition
A class should have **only one reason to change**, meaning it should perform only one job or responsibility.

### Bad Example (Violates SRP)

```python
class Report:

    def generate_report(self):
        print("Generating report...")

    def save_to_file(self):
        print("Saving report to file...")

```

### Problem:

This class has two responsibilities:

-   Generating the report
    
-   Saving the report
    

If file-saving logic changes, the class must be modified.

----------

### Good Example (Follows SRP)

```python
class Report:

    def generate_report(self):
        print("Generating report...")


class FileManager:

    def save_to_file(self, data):
        print("Saving report to file...")

```

### Explanation:

-   `Report` handles report creation.
    
-   `FileManager` handles file storage.
    
-   Each class has a single responsibility.
    


# 2. Open/Closed Principle (OCP)

## Definition

Software entities should be **open for extension but closed for modification**.

You should be able to add new functionality without changing existing code.

----------

### Bad Example

```python
class Discount:

    def calculate(self, customer_type, price):

        if customer_type == "regular":
            return price * 0.1

        elif customer_type == "premium":
            return price * 0.2

```

### Problem:

Adding a new customer type requires modifying the class.

----------

### Good Example

```python
from abc import ABC, abstractmethod

class Discount(ABC):

    @abstractmethod
    def calculate(self, price):
        pass


class RegularDiscount(Discount):

    def calculate(self, price):
        return price * 0.1


class PremiumDiscount(Discount):

    def calculate(self, price):
        return price * 0.2

```

Usage:

```python
discount = PremiumDiscount()
print(discount.calculate(1000))

```

### Explanation:

New discount types can be added without modifying existing classes.


# 3. Liskov Substitution Principle (LSP)

## Definition

Objects of a child class should be able to replace objects of the parent class **without breaking the program**.

----------

### Bad Example

```python
class Bird:
    def fly(self):
        print("Flying")


class Ostrich(Bird):
    def fly(self):
        raise Exception("Ostriches cannot fly")

```

### Problem:

`Ostrich` cannot properly substitute `Bird`.

----------

### Good Example

```python
class Bird:
    pass


class FlyingBird(Bird):
    def fly(self):
        print("Flying")


class Sparrow(FlyingBird):
    pass


class Ostrich(Bird):
    def walk(self):
        print("Walking")

```

### Explanation:

Now each subclass behaves correctly without violating expectations.



# 4. Interface Segregation Principle (ISP)

## Definition

A class should not be forced to implement methods it does not use.

Instead of one large interface, create multiple smaller ones.

----------

### Bad Example

```python
class Worker:

    def work(self):
        pass

    def eat(self):
        pass


class Robot(Worker):

    def work(self):
        print("Robot working")

    def eat(self):
        raise Exception("Robot does not eat")

```

### Problem:

Robot is forced to implement an unnecessary method.

----------

### Good Example

```python
class Workable:
    def work(self):
        pass


class Eatable:
    def eat(self):
        pass


class Human(Workable, Eatable):

    def work(self):
        print("Human working")

    def eat(self):
        print("Human eating")


class Robot(Workable):

    def work(self):
        print("Robot working")

```

### Explanation:

Classes implement only the behaviors they need.



# 5. Dependency Inversion Principle (DIP)

## Definition

High-level modules should not depend on low-level modules.  
Both should depend on abstractions.

In simple terms:  
**Depend on interfaces, not concrete classes.**

----------

### Bad Example

```python
class Keyboard:
    def type(self):
        print("Typing with keyboard")


class Computer:

    def __init__(self):
        self.keyboard = Keyboard()

```

### Problem:

`Computer` is tightly coupled with `Keyboard`.

----------

### Good Example

```python
from abc import ABC, abstractmethod

class InputDevice(ABC):

    @abstractmethod
    def type(self):
        pass


class Keyboard(InputDevice):

    def type(self):
        print("Typing with keyboard")


class TouchScreen(InputDevice):

    def type(self):
        print("Typing on touchscreen")


class Computer:

    def __init__(self, device):
        self.device = device

    def use_device(self):
        self.device.type()

```

Usage:

```python
device = TouchScreen()
computer = Computer(device)
computer.use_device()

```

### Explanation:

-   `Computer` depends on the abstraction `InputDevice`.
    
-   You can easily switch devices without modifying the computer class.
    



# Benefits of SOLID Principles

-   Improves code readability
    
-   Makes systems easier to maintain
    
-   Reduces code complexity
    
-   Encourages reusable components
    
-   Helps in writing scalable applications
    
-   Minimizes bugs during future changes
    


# Conclusion

SOLID principles are essential for writing clean object-oriented code.  
They help developers build applications that are flexible, maintainable, and easy to extend.

Applying SOLID correctly leads to professional-level software design.