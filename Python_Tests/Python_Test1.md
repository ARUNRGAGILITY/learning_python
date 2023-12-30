
### Python Intermediate Questions

#### Question 1: What is a list comprehension and provide an example of its use.

#### Question 2: Explain the difference between a shallow copy and a deep copy.

#### Question 3: How does a class inherit from another class in Python?

#### Question 4: What is a lambda function in Python?

#### Question 5: What is the difference between `@staticmethod` and `@classmethod` in Python?

#### Question 6: How do you handle exceptions in Python?

#### Question 7: What is the use of the `global` keyword in Python?

#### Question 8: Explain the difference between `break`, `continue`, and `pass` statements in Python.

#### Question 9: What are decorators in Python?

#### Question 10: What is the purpose of the `__init__` method in Python?

---
# Answer1: 
#### Question 1: What is a list comprehension and provide an example of its use.
**Answer:** A list comprehension is a concise way to create lists in Python. It consists of brackets containing an expression followed by a `for` clause, then zero or more `for` or `if` clauses. Example:
```python
squares = [x**2 for x in range(10)]
```

# Answer2:
#### Question 2: Explain the difference between a shallow copy and a deep copy.
**Answer:** A shallow copy creates a new object, but doesn't create copies of nested objects, instead it just references them. A deep copy creates a new object and recursively adds copies of nested objects. In Python, you can use the `copy` module for this purpose.

# Answer3:
#### Question 3: How does a class inherit from another class in Python?
**Answer:** In Python, a class can inherit from another class by specifying the parent class in parentheses after the class name. Example:
```python
class Parent:
    pass

class Child(Parent):
    pass
```

## Answer4:
#### Question 4: What is a lambda function in Python?
**Answer:** A lambda function in Python is a small anonymous function that can have any number of arguments, but can only have one expression. It's often used for short, simple functions that are convenient to define at the point where they are called.

## Answer5:
#### Question 5: What is the difference between `@staticmethod` and `@classmethod` in Python?
**Answer:** `@staticmethod` is used to define a method that doesn't operate on an instance or the class itself. `@classmethod`, on the other hand, is used to define a method that operates on the class and not the instance, with the class automatically passed as the first argument.
**Details:**
In Python, both `@staticmethod` and `@classmethod` are decorators that are used to define methods that are not dependent on a particular instance of a class. However, they serve different purposes and have different behaviors.

### `@staticmethod`
- A static method does not receive any reference to the instance (`self`) or the class (`cls`) as its first argument. 
- It behaves just like a plain function that happens to reside in a class's definition.
- It's used when some processing related to the class is required, but the method itself doesn't need to access any properties of the class or its instances.

**Example:**
```python
class MyClass:
    @staticmethod
    def my_static_method(arg1):
        print(f"Static method called with argument {arg1}")

MyClass.my_static_method(5)  # Call without creating an instance
```
Here, `my_static_method` is a static method that can be called without creating an instance of `MyClass`.

### `@classmethod`
- A class method receives a reference to the class (`cls`) as its first argument.
- It can access class-level properties and methods but not instance-level properties unless an instance is passed to it.
- It's often used for factory methods that return an instance of the class.

**Example:**
```python
class MyClass:
    _my_var = 10

    @classmethod
    def my_class_method(cls):
        print(f"Class method called, my_var is {cls._my_var}")

MyClass.my_class_method()  # Call without creating an instance
```
Here, `my_class_method` is a class method that can access class-level variables (`_my_var`) and is called without creating an instance of `MyClass`.

### Comparison and Use Cases
- Use a **static method** when you need a function that is logically related to the class but doesn't need to access any class or instance properties.
- Use a **class method** when you need to access or modify class state or when you need to instantiate an object of the class in a different way (factory methods).

Both `@staticmethod` and `@classmethod` allow methods to be called on the class itself, not just on instances of the class. This can be useful for utility functions or factory methods, which are common use cases in object-oriented programming.
## Answer6:
#### Question 6: How do you handle exceptions in Python?
**Answer:** Exceptions in Python are handled using `try-except` blocks. Code that may raise an exception is put in a `try` block, and the handling of exceptions is done in `except` blocks.
## Answer7:
#### Question 7: What is the use of the `global` keyword in Python?
**Answer:** The `global` keyword in Python is used to declare that a variable inside a function is global (outside the function). If you need to read and write a global variable inside a function, use `global`.
## Answer8:
#### Question 8: Explain the difference between `break`, `continue`, and `pass` statements in Python.
**Answer:** `break` exits the nearest enclosing loop, `continue` skips to the next iteration of the loop, and `pass` is a null operation; it's often used as a placeholder.
## Answer9:
#### Question 9: What are decorators in Python?
**Answer:** Decorators are a powerful and expressive feature in Python that allows you to modify or enhance functions and methods without changing their code. It's a form of metaprogramming and typically used for cross-cutting concerns like logging, performance testing, transaction management, etc.
## Answer10:
#### Question 10: What is the purpose of the `__init__` method in Python?
**Answer:** The `__init__` method in Python is a special method that's automatically called when a new instance of a class is created. It's used for initializing attributes of the object.
