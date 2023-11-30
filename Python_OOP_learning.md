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


Absolutely, let's break down each of the Object-Oriented Programming (OOP) principles in Python: Abstraction, Polymorphism, Inheritance, and Encapsulation, with more detailed step-by-step explanations and examples.

### 1. Abstraction
Abstraction is about hiding the complex implementation details and showing only the necessary features of an object. In Python, we use abstract classes and methods to achieve this.

**Step-by-Step Explanation:**
1. **Abstract Class**: It's a class that cannot be instantiated and is designed to be a blueprint for other classes. It often contains one or more abstract methods.
2. **Abstract Method**: This is a method that has a declaration but does not have an implementation. It is meant to be overridden in a subclass.

**Example:**
Let's consider an example of a vehicle as an abstract class.

```python
from abc import ABC, abstractmethod

class Vehicle(ABC):
    @abstractmethod
    def start_engine(self):
        pass

class Car(Vehicle):
    def start_engine(self):
        return "Car engine started"

class Boat(Vehicle):
    def start_engine(self):
        return "Boat engine started"
```

Here, `Vehicle` is an abstract class with an abstract method `start_engine`. `Car` and `Boat` are subclasses that provide specific implementations of `start_engine`.

### 2. Polymorphism
Polymorphism means 'many forms'. In OOP, it allows methods to do different things based on the object it's acting upon.

**Step-by-Step Explanation:**
1. **Method Overriding**: This is where a method in a subclass has the same name and type signature as a method in its superclass, but the implementation is different.

**Example:**
Expanding on our vehicle example:

```python
vehicles = [Car(), Boat()]
for vehicle in vehicles:
    print(vehicle.start_engine())
```

In this example, the method `start_engine` behaves differently for `Car` and `Boat`. This is polymorphism.

### 3. Inheritance
Inheritance is a mechanism where a new class is derived from an existing class.

**Step-by-Step Explanation:**
1. **Base Class (Parent Class)**: The class being inherited from.
2. **Derived Class (Child Class)**: The class that inherits from the Base class. It can add new attributes and methods or override existing ones.

**Example:**
Let's introduce an Electric Car that inherits from Car.

```python
class ElectricCar(Car):
    def start_engine(self):
        return "Electric Car engine started silently"

electric_car = ElectricCar()
print(electric_car.start_engine())
```

Here, `ElectricCar` inherits from `Car` and overrides the `start_engine` method.

### 4. Encapsulation
Encapsulation is the bundling of data (variables) and methods (functions) that operate on the data into a single unit, or class. It also restricts direct access to some of an object's components.

**Step-by-Step Explanation:**
1. **Private Members**: In Python, we use the double underscore `__` prefix to make an attribute or method private.
2. **Public Methods**: These are used to access and modify the private members.

**Example:**
Let's encapsulate the data in a class.

```python
class Laptop:
    def __init__(self):
        self.__price = 500

    def get_price(self):
        return self.__price

    def set_price(self, price):
        if price > 0:
            self.__price = price

laptop = Laptop()
print(laptop.get_price())  # Accessing price

laptop.set_price(600)
print(laptop.get_price())  # Modified price
```

In this example, `__price` is a private attribute. `get_price` and `set_price` are public methods to read and modify the price.

These examples and explanations should provide a clearer understanding of the four fundamental OOP principles in Python. Each concept is crucial for designing robust, reusable, and maintainable code in an object-oriented way.
