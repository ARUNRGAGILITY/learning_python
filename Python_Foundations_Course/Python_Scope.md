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
