## Python function is a reusable block of code 
## that helps to process with an input and return an output

# def function_name(parameter1, parameter2, parameter3):
#      print(f" This is a function {parameter1}, {parameter2}, {parameter3}")
#      sum = parameter1 + parameter2 + parameter3
#      return sum


# 

# Simple Function
```
def greet():
    print("Hello, World!")

# Calling the function
greet()
```


# Function with a Parameter
```
def greet(name):
    print(f"Hello, {name}!")

# Calling the function
greet("Alice")
```



# Function with return value
```
def add(a, b):
    return a + b

# Calling the function
result = add(5, 3)
print(f"Result: {result}")

```


# Function with Multiple return values
```
def arithmetic_operations(a, b):
    return a+b, a-b, a*b, a/b

# Calling the function
sum, difference, product, division = arithmetic_operations(10, 5)
print(f"Sum: {sum}, Difference: {difference}, Product: {product}, Division: {division}")
```


# Function with Default Parameters
```
def greet(name, msg="Good morning!"):
    print(f"Hello, {name}, {msg}")
    
    

# Calling the function
greet("Bob")
greet("Bob", "How are you?")
```


# Function with keyword arguments
```
def introduce(name, age):
    print(f"My name is {name} and I am {age} years old.")

# Calling the function
introduce(name="Charlie", age=30)
```


# Function with Arbitary Arguments
```
def fruits(*args):
    for fruit in args:
        print(fruit)

# Calling the function
fruits("apple", "banana", "cherry")
```


# Function with Arbitary Keyword Arguments
```
def person_info(**kwargs):
    for key, value in kwargs.items():
        print(f"{key}: {value}")

# Calling the function
person_info(name="David", age=40, city="New York")
```


# Recursive Function
```
def factorial(n):
    if n == 1:
        return 1
    else:
        return n * factorial(n-1)

# Calling the function
print("Factorial of 5:", factorial(5))
```


# Lambda Function
```
square = lambda x: x ** 2

# Calling the function
print("Square of 4:", square(4))

```


# Function with Global Variable
```
x = "global"

def func():
    print("x inside:", x)

# Calling the function
func()

```


# Function with Local variable
```
def func():
    y = "local"
    print("Inside function:", y)

# Calling the function
func()

```


# Function with Non local variable
```
def outer():
    x = "local"
    def inner():
        nonlocal x
        x = "nonlocal"
        print("inner:", x)
    inner()
    print("outer:", x)

# Calling the function
outer()

```


# Function with DocString
```
def multiply(a, b):
    """
    Multiply two numbers and return the result.
    """
    return a * b

# Calling the function
print("Product of 3 and 4:", multiply(3, 4))
```



# Function with returning function
```
def make_multiplier(n):
    def multiplier(x):
        return x * n
    return multiplier

# Calling the function
times3 = make_multiplier(3)
print("3 times 5:", times3(5))

```


# Nested Function
```
def outer():
    def inner():
        print("Inner function")
    inner()

# Calling the function
outer()
```


# Function with variable length positional, keyword
```
def mix_args(*args, **kwargs):
    print("Positional arguments:", args)
    print("Keyword arguments:", kwargs)

# Calling the function
mix_args(1, 2, a=3, b=4)
```


# Generator Function
# Defining the generator function countdown
```
def countdown(n):
    while n > 0:
        yield n
        n -= 1

# Creating a generator object
countdown_generator = countdown(3)

# Demonstrating the resumption of the generator
# Fetching the first value
first_value = next(countdown_generator)
# Fetching the second value
second_value = next(countdown_generator)
# Fetching the third and final value
third_value = next(countdown_generator)

print("Generator function: ", first_value, second_value, third_value)

```
        

# Function with Type Hints
```
def greeting(name: str) -> str:
    return f'Hello, {name}'

message  = greeting("John")
print(message)

```


# Function with exception/error handling
```
def divide(x, y):
    try:
        result = x / y
    except ZeroDivisionError:
        print("division by zero!")
    else:
        return result
```
    
# Function with List compression
```
def squares(n):
    return [i**2 for i in range(n)]

print(f"The square of square(2) {square(2)}")
```

# Function with Map and Filter
```
def filter_even(numbers):
    return list(filter(lambda x: x % 2 == 0, numbers))

numbers_list = [3, 2, 4, 7, 9, 21, 24]
even_nos = filter_even(numbers_list)
print(f"Even Numbers from {numbers_list} is {even_nos}")
```

# Function with Decorator
```
def my_decorator(func):
    def wrapper():
        print("Something is happening before the function is called.")
        func()
        print("Something is happening after the function is called.")
    return wrapper

@my_decorator
def say_hello():
    print("Hello!")
```


# Function with *args and Default Parameters
```
def greet_all(msg="Hello", *names):
    for name in names:
        print(f"{msg}, {name}")

```

## Python pass/by value or reference/is by object
## Immutable: int, float, str, tuples
## Mutable: list, dictionaries, sets
```
def modify_list(lst):
    lst.append(4)
    return lst

def modify_number(num):
    num += 10
    return num

# Mutable object example (list)
my_list = [1, 2, 3]
print("Original List:", my_list)
modify_list(my_list)
print("Modified List:", my_list)

# Immutable object example (integer)
my_number = 5
print("\nOriginal Number:", my_number)
modify_number(my_number)
print("Modified Number:", my_number)

```
