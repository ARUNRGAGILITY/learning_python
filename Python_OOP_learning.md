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


Let's expand on each of the OOP principles with more detailed examples to deepen your understanding.

### 1. Abstraction

Abstraction is about focusing on what an object does, rather than how it does it. It's implemented using abstract classes and methods.

**Further Example:**

Let's create an abstract class `Animal` and derive different animal classes from it.

```python
from abc import ABC, abstractmethod

class Animal(ABC):
    @abstractmethod
    def sound(self):
        pass

class Dog(Animal):
    def sound(self):
        return "Bark!"

class Cat(Animal):
    def sound(self):
        return "Meow"

# Usage
dog = Dog()
cat = Cat()
print(dog.sound())  # Output: Bark!
print(cat.sound())  # Output: Meow
```

In this example, `Animal` is an abstract class with an abstract method `sound`. `Dog` and `Cat` are concrete classes implementing their version of `sound`.

### 2. Polymorphism

Polymorphism allows us to define methods in the child class with the same name as defined in their parent class.

**Further Example:**

Let's extend the `Animal` class with a method `info` that behaves differently for each animal.

```python
class Dog(Animal):
    def sound(self):
        return "Bark!"

    def info(self):
        return "Dogs are loyal."

class Cat(Animal):
    def sound(self):
        return "Meow"

    def info(self):
        return "Cats love independence."

animals = [Dog(), Cat()]
for animal in animals:
    print(animal.info())
```

Each animal class (`Dog` and `Cat`) has its own implementation of `info`, showcasing polymorphism.

### 3. Inheritance

Inheritance allows us to define a class that inherits all the methods and properties from another class.

**Further Example:**

Let's create a base class `Vehicle` and then derive different types of vehicles from it.

```python
class Vehicle:
    def general_usage(self):
        return "Transportation"

class Car(Vehicle):
    def specific_usage(self):
        return "Commute to work"

class Truck(Vehicle):
    def specific_usage(self):
        return "Transport goods"

car = Car()
truck = Truck()
print(car.general_usage())  # Inherited method
print(car.specific_usage())  # Specific to Car
```

`Car` and `Truck` inherit from `Vehicle` and have their own specific usage method.

### 4. Encapsulation

Encapsulation involves keeping the internal state of an object safe from external modification.

**Further Example:**

Let's create a `BankAccount` class that encapsulates the balance and provides methods to deposit or withdraw money.

```python
class BankAccount:
    def __init__(self):
        self.__balance = 0  # Private attribute

    def deposit(self, amount):
        if amount > 0:
            self.__balance += amount
            return "Deposit successful"

    def withdraw(self, amount):
        if 0 < amount <= self.__balance:
            self.__balance -= amount
            return "Withdrawal successful"
        return "Insufficient balance"

    def get_balance(self):
        return self.__balance

account = BankAccount()
print(account.deposit(1000))
print(account.get_balance())
print(account.withdraw(500))
print(account.get_balance())
```

In this example, the balance is a private attribute. The `deposit`, `withdraw`, and `get_balance` methods are used to interact with the balance.

These additional examples should help in understanding how to apply the principles of OOP in different contexts. Each concept is instrumental in building a solid foundation in object-oriented programming in Python.

#### Public, Private, Protected Definitions

In Python, access control for class members (attributes and methods) is achieved through naming conventions for public, private, and protected members. Understanding these is key to implementing encapsulation effectively.

### Public Members
- **Definition**: Public members are accessible from outside the class. The use of public members is safe and intended.
- **Naming Convention**: Regular method or attribute names, e.g., `name` or `method_name()`.
- **Example**: A class method that's intended to be used freely by the instances of the class and outside of the class.

### Private Members
- **Definition**: Private members are intended to be used only within the class. Accessing them outside the class leads to a naming error.
- **Naming Convention**: Name prefixed with two underscores, e.g., `__name` or `__method_name()`.
- **Example**: An attribute that should not be accessible directly from outside of the class, such as internal state or helper methods.

### Protected Members
- **Definition**: Protected members are intended for use within the class and subclasses. They are accessible from outside the class, but this is considered bad practice.
- **Naming Convention**: Name prefixed with a single underscore, e.g., `_name` or `_method_name()`.
- **Example**: An attribute that is meant to be used within the class and subclasses, indicating a more internal use than public members.

### Tabular Summary

| Access Type | Naming Convention   | Accessible From           | Example Usage                                 |
|-------------|---------------------|---------------------------|-----------------------------------------------|
| Public      | `name`, `method()`  | Anywhere                  | `obj.name`, `obj.method()`                    |
| Protected   | `_name`, `_method()`| Class and subclasses      | For subclassing, internal variables/methods   |
| Private     | `__name`, `__method()`| Within the class only    | Internal workings of the class, helper methods|

### Detailed Example

Here's a class example showcasing public, protected, and private members:

```python
class ExampleClass:
    def __init__(self):
        self.public_var = "I am public"
        self._protected_var = "I am protected"
        self.__private_var = "I am private"

    def public_method(self):
        return "This is a public method"

    def _protected_method(self):
        return "This is a protected method"

    def __private_method(self):
        return "This is a private method"

# Creating an instance of ExampleClass
example = ExampleClass()

# Accessing public members
print(example.public_var)         # Accessible
print(example.public_method())    # Accessible

# Accessing protected members
print(example._protected_var)     # Technically accessible, but not recommended
print(example._protected_method()) # Technically accessible, but not recommended

# Accessing private members
# print(example.__private_var)      # Will raise an AttributeError
# print(example.__private_method()) # Will raise an AttributeError
```

In practice, while Python doesn't enforce access restrictions as strictly as languages like Java or C++, it's a convention and good practice to adhere to these access control mechanisms for better code organization and encapsulation.

#### Usage Examples of Public, Protected and Private members / methods

Let's use real-world examples to illustrate when to use public, protected, and private variables and methods in Python, making it easier for beginners to understand.

### 1. Public Members
**Real-world Example**: Consider a `Car` class. Public attributes/methods are like the features of the car that are accessible to everyone, like the car model, color, or the ability to start the engine.

**When to Use**: Use public members when they need to be accessed freely, both within the class and from outside of it.

```python
class Car:
    def __init__(self, model, color):
        self.model = model  # Public attribute
        self.color = color  # Public attribute

    def start_engine(self):  # Public method
        return "Engine started"

# Usage
my_car = Car("Tesla Model S", "Red")
print(my_car.model)  # Accessible
print(my_car.start_engine())  # Accessible
```

### 2. Protected Members
**Real-world Example**: Think of a `BankAccount` class. Protected members are like the ledger balance, which should be accessible to the bank and its subsidiaries but not to the general public.

**When to Use**: Use protected members when they are intended for use within the class and its subclasses but not outside of these.

```python
class BankAccount:
    def __init__(self):
        self._balance = 0  # Protected attribute

    def deposit(self, amount):
        if amount > 0:
            self._balance += amount
            return "Deposit successful"

class SavingsAccount(BankAccount):
    def calculate_interest(self):
        return self._balance * 0.05  # Accessing protected attribute

# Usage
saving_acc = SavingsAccount()
saving_acc.deposit(1000)
print(saving_acc.calculate_interest())  # Accessible within subclass
```

### 3. Private Members
**Real-world Example**: Imagine a `Computer` class. Private members are like the internal components of the computer, such as the motherboard or CPU, which should not be tampered with by the users.

**When to Use**: Use private members when they are not intended to be accessed from outside the class. They are typically used for internal workings and helper methods.

```python
class Computer:
    def __init__(self):
        self.__cpu = "Intel Core i7"  # Private attribute

    def __cooling_system(self):  # Private method
        return "Cooling system active"

    def start_computer(self):
        self.__cooling_system()  # Accessing private method
        return "Computer started with " + self.__cpu

# Usage
my_computer = Computer()
print(my_computer.start_computer())  # Accessible
# print(my_computer.__cpu)  # Will raise an AttributeError
```

In these examples, the **public members** are accessible to everyone, the **protected members** are intended for internal use and subclasses, and the **private members** are exclusively used within the class itself. This distinction helps manage and protect the data and functionality of your classes, leading to more robust and maintainable code.

#### Examples of Public, Protected and Private variables and methods in details

Let's explore four additional examples to demonstrate the use of public, protected, and private variables and methods in Python classes, each in a different context.

### Example 1: Library Management System

```python
class Library:
    def __init__(self):
        self.books = []  # Public attribute
        self._catalogue = {}  # Protected attribute
        self.__database_access = "Access Key"  # Private attribute

    def add_book(self, book):  # Public method
        self.books.append(book)
        self._update_catalogue(book)

    def _update_catalogue(self, book):  # Protected method
        if book in self._catalogue:
            self._catalogue[book] += 1
        else:
            self._catalogue[book] = 1

    def __database_connect(self):  # Private method
        return f"Connecting to database with {self.__database_access}"

    def check_availability(self, book):
        self.__database_connect()  # Using private method
        return self._catalogue.get(book, 0) > 0

# Usage
library = Library()
library.add_book("Python 101")
print(library.books)  # Public attribute
print(library.check_availability("Python 101"))  # Using public method
```

### Example 2: Online Shopping System

```python
class ShoppingCart:
    def __init__(self):
        self.items = []  # Public attribute
        self._total = 0  # Protected attribute
        self.__discount_code = "SECRET100"  # Private attribute

    def add_item(self, item, price):  # Public method
        self.items.append(item)
        self._update_total(price)

    def _update_total(self, price):  # Protected method
        self._total += price

    def __apply_discount(self):  # Private method
        self._total *= 0.9

    def checkout(self):
        self.__apply_discount()
        return f"Total after discount: {self._total}"

# Usage
cart = ShoppingCart()
cart.add_item("Laptop", 1000)
print(cart.items)  # Public attribute
print(cart.checkout())  # Using public method
```

### Example 3: Social Media Profile

```python
class SocialMediaProfile:
    def __init__(self, username):
        self.username = username  # Public attribute
        self._followers = 0  # Protected attribute
        self.__password = "SuperSecret"  # Private attribute

    def follow(self):  # Public method
        self._followers += 1

    def _show_followers(self):  # Protected method
        return f"Followers: {self._followers}"

    def __login(self):  # Private method
        return f"Logging in with password {self.__password}"

    def post_update(self):
        if self.__login():  # Using private method
            return "Posted an update"

# Usage
profile = SocialMediaProfile("user123")
profile.follow()
print(profile.username)  # Public attribute
print(profile.post_update())  # Using public method
```

### Example 4: Vehicle System

```python
class Vehicle:
    def __init__(self, make, model):
        self.make = make  # Public attribute
        self.model = model  # Public attribute
        self._mileage = 0  # Protected attribute
        self.__engine_number = "123456789"  # Private attribute

    def drive(self, distance):  # Public method
        self._mileage += distance

    def _show_mileage(self):  # Protected method
        return f"Mileage: {self._mileage} km"

    def __engine_check(self):  # Private method
        return f"Engine Number: {self.__engine_number} is OK"

    def perform_maintenance(self):
        return self.__engine_check()  # Using private method

# Usage
car = Vehicle("Toyota", "Corolla")
car.drive(100)
print(f"{car.make} {car.model}")  # Public attributes
print(car.perform_maintenance())  # Using public method
```

Each example illustrates a different scenario where public, protected, and private members are used in a Python class, demonstrating their applicability in real-world applications. Public members are openly accessible, protected members are meant for internal and subclass usage, and private members are strictly for internal class operations.

