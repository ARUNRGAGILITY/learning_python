### Python Intermediate MCQs

#### Question 1
What will be the output of the following code?
```python
print(bool(None))
```
a) `True`  
b) `False`  
c) `None`  
d) Error

#### Question 2
What does the following list comprehension do?
```python
[x*2 for x in range(5)]
```
a) Doubles the range object  
b) Creates a list of the first 5 even numbers  
c) Syntax Error  
d) None of the above

#### Question 3
Which method of a dictionary object in Python is used to get the value associated with a key?
a) `get(key)`  
b) `key()`  
c) `value()`  
d) `items()`

#### Question 4
What is the output of the following code?
```python
def some_func():
    try:
        return 'from_try'
    finally:
        return 'from_finally'

print(some_func())
```
a) `from_try`  
b) `from_finally`  
c) `None`  
d) Error

#### Question 5
What is the term used for inserting an object in a specific index in a list?
a) append  
b) insert  
c) extend  
d) push

#### Question 6
Which of the following is used to define a block of code in Python language?
a) Brackets  
b) Indentation  
c) Key  
d) None of the above

#### Question 7
What will be the output of the following code?
```python
x = 0
while (x < 3):
    print(x)
    x++
```
a) 0 1 2  
b) 0 1 2 3  
c) Syntax Error  
d) None of the above

#### Question 8
What does the `*args` parameter in function definitions do?
a) Accepts any number of positional arguments  
b) Accepts exactly one argument  
c) Accepts any number of keyword arguments  
d) Syntax Error

#### Question 9
What is the correct way to create a regular expression in Python?
a) `re.compile('pattern')`  
b) `re.regex('pattern')`  
c) `regex.compile('pattern')`  
d) `re('pattern')`

#### Question 10
Which of the following is correct about Python?
a) It supports automatic garbage collection.  
b) It can be easily integrated with C, C++, and JAVA.  
c) Both a and b  
d) None of the above

#### Question 11
What is the output of the following code?
```python
print(type(lambda x: x+1))
```
a) `int`  
b) `<class 'function'>`  
c) `<class 'lambda'>`  
d) `NoneType`

#### Question 12
Which function overloads the `+` operator in Python?
a) `__add__()`  
b) `__plus__()`  
c) `__sum__()`  
d) `__concat__()` 

#### Question 13
What does the `yield` keyword do in Python?
a) It is used to raise an exception  
b) It ends a function  
c) It returns a value from a generator  
d) It is a shorthand for `yield from`

#### Question 14
Which of the following is not a valid Python datatype?
a) List  
b) Dictionary  
c) Tuple  
d) Class

#### Question 15
What will be the output of the following code?
```python
list = ['1', '2', '3']
list.append('4')
print(list)
```
a) `['1', '2', '3', 4]`  
b) `['1', '2', '3', '4']`  
c) Syntax Error  
d) None of the above

#### Question 16
Which of the following is not a core data type in Python?
a) Lists  
b) Dictionary  
c) Tuples  
d) Class

#### Question 17
What will be the output of the following code?
```python
def func(a, b=5, c=10):
    print('a is', a, 'and b is', b, 'and c is', c)

func(3, 7)
```
a) a is 3 and b is 7 and c is 10  
b) a is 3 and b is 5 and c is 10  
c) a is 3 and b is 5 and c is 7  
d) Syntax Error

#### Question 18
What does the `enumerate` function in Python do?


a) Returns an enumerate object  
b) Converts a tuple into an enumerate object  
c) Adds a counter to an iterable and returns it  
d) None of the above

#### Question 19
What will be the output of the following code?
```python
if None:
    print("Hello")
else:
    print("Goodbye")
```
a) Hello  
b) Goodbye  
c) None  
d) Error

#### Question 20
Which of the following is the correct way to create a set in Python?
a) `{1, 2, 3}`  
b) `set(1, 2, 3)`  
c) `set([1, 2, 3])`  
d) Both a and c

#### Question 21
What is the output of the following code?
```python
a = [1, 2, 3]
b = a
b.append(4)
print(a)
```
a) `[1, 2, 3]`  
b) `[1, 2, 3, 4]`  
c) `[1, 2, 4]`  
d) Syntax Error

#### Question 22
What is the correct syntax for defining a class in Python?
a) `class MyClass():`  
b) `class MyClass:`  
c) `class MyClass{}:`  
d) `class MyClass[]:`

#### Question 23
What will be the output of the following code?
```python
a = True
b = False
c = False
  
if a or b and c:
    print("PYTHONISGREAT")
else:
    print("pythonisgreat")
```
a) PYTHONISGREAT  
b) pythonisgreat  
c) True  
d) False

#### Question 24
What is slicing in Python?
a) Removing items from a list  
b) Accessing a range of elements in a sequence  
c) Dividing a string into substrings  
d) None of the above

#### Question 25
What is the output of the following code?
```python
x = 1
y = 2
z = 3

print(x < y < z)
```
a) True  
b) False  
c) Error  
d) None of the above

---
Here are the answers and explanations for the 25 Python multiple-choice questions:

#### Answer 1
b) `False`  
**Explanation:** `None` is a special constant in Python that represents the absence of a value. When converted to a boolean, it is considered `False`.

#### Answer 2
b) Creates a list of the first 5 even numbers  
**Explanation:** The list comprehension `[x*2 for x in range(5)]` creates a list by multiplying each number in the range 0 to 4 by 2, resulting in the first 5 even numbers [0, 2, 4, 6, 8].

#### Answer 3
a) `get(key)`  
**Explanation:** The `get` method of a dictionary object is used to retrieve the value associated with a specified key.

#### Answer 4
b) `from_finally`  
**Explanation:** In Python, if both `try` and `finally` blocks have return statements, the `finally` block’s return statement will always execute.

#### Answer 5
b) insert  
**Explanation:** The `insert` method is used to insert an object at a specific index in a list.

#### Answer 6
b) Indentation  
**Explanation:** Python uses indentation to define blocks of code, unlike many other languages which use brackets.

#### Answer 7
c) Syntax Error  
**Explanation:** Python does not support the `++` operator for incrementing. The correct way to increment `x` in Python is `x += 1`.

#### Answer 8
a) Accepts any number of positional arguments  
**Explanation:** `*args` allows a function to accept any number of positional arguments.

#### Answer 9
a) `re.compile('pattern')`  
**Explanation:** The `re.compile` function in the `re` (regular expression) module is used to compile a regular expression pattern into a regular expression object.

#### Answer 10
c) Both a and b  
**Explanation:** Python supports automatic garbage collection and can be easily integrated with C, C++, and JAVA.

#### Answer 11
b) `<class 'function'>`  
**Explanation:** In Python, a lambda function is still a function, so its type is `<class 'function'>`.

#### Answer 12
a) `__add__()`  
**Explanation:** The `__add__()` method is a special method used to overload the `+` operator in Python.

#### Answer 13
c) It returns a value from a generator  
**Explanation:** The `yield` keyword is used in a function to turn it into a generator. It returns a value and pauses the function, maintaining its state for subsequent calls.

#### Answer 14
d) Class  
**Explanation:** List, Dictionary, and Tuple are built-in data types in Python. Class is not a data type, but a construct for creating objects.

#### Answer 15
b) `['1', '2', '3', '4']`  
**Explanation:** The `append` method adds an item to the end of the list. The item `'4'` is added as a string, not an integer.

#### Answer 16
d) Class  
**Explanation:** Lists, Dictionaries, and Tuples are core data types in Python. Class is a construct for object-oriented programming, not a data type.

#### Answer 17
a) a is 3 and b is 7 and c is 10  
**Explanation:** The function is called with `a=3` and `b=7`. Since `c` is not provided, it uses its default value of `10`.

#### Answer 18
c) Adds a counter to an iterable and returns it  
**Explanation:** The `enumerate` function adds a counter to an iterable and returns it as an enumerate object.

#### Answer 19
b) Goodbye  
**Explanation:** In Python, `None` is considered `False` in conditional statements. Therefore, the else block is executed.

#### Answer 20
d) Both a and c  
**Explanation:** Both `{1, 2, 3}` and `set([1, 2, 3])` are correct ways to create a set in Python.

#### Answer 21
b) `[1, 2, 3, 4]`  
**Explanation:** `b` is a reference to the same list as `a`. Modifying `b` also modifies `a`.

#### Answer 22
b) `class MyClass:`  
**Explanation:** The correct syntax to define a class in Python is `class MyClass:`.

#### Answer 23
a) PYTHONISGREAT  
**Explanation:** In Python, the `or` and `and` operators follow short-circuit evaluation. Since `a` is `True`, the `or` expression is `True` regardless of the `and` part.

#### Answer 24


b) Accessing a range of elements in a sequence  
**Explanation:** Slicing in Python is a feature that enables accessing parts of sequences like strings, lists, and tuples using a range of indices.

#### Answer 25
a) True  
**Explanation:** The expression `x < y < z` is equivalent to `x < y and y < z`, which is `True` in this case.

---
