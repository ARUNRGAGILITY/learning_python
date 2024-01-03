# Python Scope

In Python, variable scope refers to the context in which a variable is recognized. There are four main scopes:

1. **Local Scope**: Variables created within a function are in the local scope of that function. They are only accessible inside the function and not outside of it.

2. **Enclosing Scope**: This involves nested functions - a function defined inside another function. Variables in the enclosing scope are accessible in the nested function but not outside the outer function.

3. **Global Scope**: Variables created in the main body of a Python script are global and are accessible throughout the script, including inside functions, unless shadowed by a local variable with the same name.

4. **Built-in Scope**: These are special names that Python reserves for itself. For example, `print`, `id` are in the built-in scope and are always available.

Here's an example to illustrate these scopes:

```python
x = "global"  # Global scope

def outer():
    x = "outer local"  # Enclosing scope relative to inner()

    def inner():
        x = "inner local"  # Local scope
        print("Inner:", x)

    inner()
    print("Outer:", x)

print("Global:", x)
outer()
```

This code will output:

```
Global: global
Inner: inner local
Outer: outer local
```

- The `x` inside `inner()` function is in the local scope of `inner()`.
- The `x` inside `outer()` is in the enclosing scope relative to `inner()`.
- The `x` outside of all functions is in the global scope.

If you want to modify a global variable inside a function, you must use the `global` keyword. Similarly, to modify a variable in the enclosing scope, use the `nonlocal` keyword.


## Examples of different types of Scope: Local, Enclosing, Built-in, and Global Scopes

### 1. Local Scope

Local variables are defined within a function and can only be used within that function.

#### Example 1: Basic Local Variable
```python
def function():
    local_var = "I am local"
    print(local_var)

function()  # prints "I am local"
# print(local_var)  # This will raise an error as local_var is not accessible outside the function.
```

#### Example 2: Local Variable Shadowing
```python
x = "global"

def function():
    x = "local"
    print(x)  # prints "local"

function()
print(x)  # prints "global"
```

#### Example 3: Local Variable in Loop
```python
def function():
    for i in range(3):
        loop_var = i
        print(loop_var)  # prints 0, 1, 2

function()
# print(loop_var)  # This will raise an error as loop_var is not accessible outside the function.
```

#### Example 4: Local Variable in Conditional Statement
```python
def function(flag):
    if flag:
        conditional_var = "Yes"
        print(conditional_var)
    else:
        conditional_var = "No"
        print(conditional_var)

function(True)  # prints "Yes"
# print(conditional_var)  # This will raise an error as conditional_var is not accessible outside the function.
```

#### Example 5: Function Parameter as Local Variable
```python
def function(param):
    print(param)  # prints the value passed to the function

function("I'm a parameter")  # prints "I'm a parameter"
# print(param)  # This will raise an error as param is not accessible outside the function.
```

### 2. Enclosing Scope

Variables in the enclosing scope are those defined in a function that is wrapped by another function.

#### Example 1: Simple Enclosing Scope
```python
def outer():
    enclosing_var = "outer"

    def inner():
        print(enclosing_var)

    inner()

outer()  # prints "outer"
# print(enclosing_var)  # Error: enclosing_var is not accessible outside outer().
```

#### Example 2: Modifying Enclosing Variable
```python
def outer():
    enclosing_var = "outer"

    def inner():
        nonlocal enclosing_var
        enclosing_var = "inner modified"
        print(enclosing_var)

    inner()
    print(enclosing_var)  # prints "inner modified"

outer()
```

#### Example 3: Multiple Nested Functions
```python
def outer():
    enclosing_var = "outer"

    def inner1():
        def inner2():
            print(enclosing_var)
        inner2()

    inner1()

outer()  # prints "outer"
```

#### Example 4: Enclosing Loop Variable
```python
def outer():
    for i in range(3):
        enclosing_var = f"outer {i}"

        def inner():
            print(enclosing_var)

        inner()

outer()  # prints "outer 0", "outer 1", "outer 2"
```

#### Example 5: Conditional in Enclosing Scope
```python
def outer(flag):
    if flag:
        enclosing_var = "Yes"

        def inner():
            print(enclosing_var)

        inner()
    else:
        enclosing_var = "No"

        def inner():
            print(enclosing_var)

        inner()

outer(True)  # prints "Yes"
outer(False) # prints "No"
```

### 3. Global Scope

Global variables are defined at the top level of a module or declared global inside a function.

#### Example 1: Basic Global Variable
```python
global_var = "I am global"

def function():
    print(global_var)

function()  # prints "I am global"
print(global_var)  # prints "I am global"
```

#### Example 2: Modifying Global Variable
```python
global_var = "initial"

def function():
    global global_var
    global_var = "modified"

function()
print(global_var)  # prints "modified"
```

#### Example 3: Global Variable Shadowed by Local
```python
global_var = "global"

def function():
    global_var = "local"
    print(global_var)  # prints "local"

function()
print(global_var)  # prints "global"
```

#### Example 4: Global Variable in Loop
```python
global_var = 0

def function():
    global global_var
    for i in range(5):
        global_var = i

function()
print(global_var)  # prints 4
```

#### Example 5: Global Variable in Conditional Statement
```python
global_var = "initial"

def

 function(flag):
    global global_var
    if flag:
        global_var = "Yes"
    else:
        global_var = "No"

function(True)
print(global_var)  # prints "Yes"
```

### 4. Built-in Scope

Built-in scope refers to names that are preassigned in Python.

#### Example 1: Using `len` Function
```python
print(len([1, 2, 3]))  # prints 3, len is a built-in function
```

#### Example 2: Using `max` Function
```python
print(max(1, 2, 3))  # prints 3, max is a built-in function
```

#### Example 3: Using `type` Function
```python
print(type(123))  # prints <class 'int'>, type is a built-in function
```

#### Example 4: Using `print` Function
```python
print("Hello, World!")  # print is a built-in function
```

#### Example 5: Using `int` Function
```python
print(int("123"))  # prints 123, int is a built-in function
```


