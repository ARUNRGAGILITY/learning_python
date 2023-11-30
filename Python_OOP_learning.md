Object-Oriented Programming (OOP) in Python revolves around four primary principles: Abstraction, Polymorphism, Inheritance, and Encapsulation. Let's dive into each of these concepts with examples:

### 1. Abstraction
Abstraction means hiding the complex reality while exposing only the necessary parts. In Python, abstraction is often achieved using abstract classes and methods.

Here's an example:

```python
from abc import ABC, abstractmethod

class Shape(ABC):
    @abstractmethod
    def area(self):
        pass

    @abstractmethod
    def perimeter(self):
        pass

class Rectangle(Shape):
    def __init__(self, length, width):
        self.length = length
        self.width = width

    def area(self):
        return self.length * self.width

    def perimeter(self):
        return 2 * (self.length + self.width)
```

In this example, `Shape` is an abstract class with abstract methods `area` and `perimeter`. `Rectangle` is a concrete class that implements these methods.

### 2. Polymorphism
Polymorphism allows methods to do different things based on the object it is acting upon. 

Here's an example using the previously defined `Shape` class:

```python
class Circle(Shape):
    def __init__(self, radius):
        self.radius = radius

    def area(self):
        return 3.14 * self.radius * self.radius

    def perimeter(self):
        return 2 * 3.14 * self.radius

# Using polymorphism
shapes = [Rectangle(2,3), Circle(1)]
for shape in shapes:
    print(f"Area: {shape.area()}, Perimeter: {shape.perimeter()}")
```

In this example, the `area` and `perimeter` methods behave differently based on whether they are called on a `Rectangle` or a `Circle`.

### 3. Inheritance
Inheritance allows new classes to inherit the properties and methods of existing classes.

Here's an example:

```python
class Square(Rectangle):
    def __init__(self, side):
        super().__init__(side, side)
```

In this example, `Square` is a subclass of `Rectangle` and inherits its methods and properties. The `super().__init__(side, side)` call initializes the `Rectangle` part of the `Square`.

### 4. Encapsulation
Encapsulation involves bundling of data and methods that work on that data within one unit, often restricting access to some of the object’s components.

Here's an example:

```python
class Computer:
    def __init__(self):
        self.__max_price = 900

    def sell(self):
        print(f"Selling Price: {self.__max_price}")

    def set_max_price(self, price):
        if price > 800:
            self.__max_price = price

c = Computer()
c.sell()

# trying to change the price directly will not work
c.__max_price = 1000
c.sell()

# using setter function
c.set_max_price(1000)
c.sell()
```

In this example, `__max_price` is a private variable, accessible only inside the class. We use a method `set_max_price` to modify it, which is an example of encapsulation.
