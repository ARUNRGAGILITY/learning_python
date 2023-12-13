Decorators in Python are a very powerful and useful tool, allowing you to modify the behavior of functions or methods.
A decorator is essentially a function that takes another function as an argument and extends its behavior without explicitly modifying it. 

### Basic Decorator Example

First, let's start with a simple example of a decorator that logs information before and after a function execution:

```python
def my_decorator(func):
    def wrapper():
        print("Something is happening before the function is called.")
        func()
        print("Something is happening after the function is called.")
    return wrapper

@my_decorator
def say_hello():
    print("Hello!")

say_hello()
```

In this example, `my_decorator` is a decorator that wraps the function `say_hello`. The `wrapper` function inside `my_decorator` adds behavior (printing messages) before and after the call to `say_hello`.

### Decorator with Arguments

Now, let's see an example where the decorator takes arguments:

```python
def repeat(num_times):
    def decorator_repeat(func):
        def wrapper(*args, **kwargs):
            for _ in range(num_times):
                result = func(*args, **kwargs)
            return result
        return wrapper
    return decorator_repeat

@repeat(num_times=3)
def greet(name):
    print(f"Hello {name}")

greet("Alice")
```

In this example, `repeat` is a decorator factory that takes an argument `num_times`. It returns the actual decorator `decorator_repeat`, which then applies the given function `num_times`.

### Decorator for Timing Function Execution

A practical use of decorators is to measure the execution time of a function:

```python
import time

def timer(func):
    def wrapper(*args, **kwargs):
        start_time = time.time()
        result = func(*args, **kwargs)
        end_time = time.time()
        print(f"Executing {func.__name__} took {end_time - start_time} seconds.")
        return result
    return wrapper

@timer
def long_running_function():
    time.sleep(2)

long_running_function()
```

In this `timer` decorator, the wrapper function measures the time before and after the execution of `long_running_function` and prints the total execution time.

These examples demonstrate the versatility of decorators in Python. 
You can use them for logging, timing, enforcing access control, and much more, making them a very handy feature for efficient and cleaner code.
