# Module1: Introduction

## Python Output Statements
```python
# Python output statement using print function/statement
my_name = "Arjun"
# printing using double-quotes, single-quote, f-string, and comma options
print("Hello World!")
print('Hello World!')
print(f"Hello World! {my_name}")

## some more options for printing
a_num = 10
b_num = 20
c_str = "John"
d_str = "Arjun"
print("This is a sample print statement ", a_num,b_num,c_str,d_str)
# expressions
print("This is a sample print statement ", a_num + b_num,c_str,d_str)
```
## Python basic Data types
### Basic data types are int, float, complex numbers, string, and boolean
```python
a = 10
b = 30
c = 20.22
d = 45.85
cnum = 5 + 3j
my_name = "John Star"
is_contractor = True
is_employee = False

# printing the values
print(f"=====================")
print(f"Integer values: ",a,b)
print(f"Float Values: {c} and {d}")
print(f"Complex Number: {cnum}")
print(f"String variable: {my_name}")
print(f"{my_name} is a contractor {is_contractor} and an employee {is_employee}")
print(f"=====================")
```

## Python Input Statements
```python
user_input_name = str(input("Enter your name: "))
print(f"You have entered: {user_input_name}")
```

## Python Comments

Python comments start with '#' at the beginning, as shown in the earlier examples in this module.

## Python Programs
Python programs are written with indentation, as follows

```python
a = 10
b = 20
if a == b :
  print(f" a is equal to b")
  if a != b :
    print("another if statement")
  else:
    print("another else statement")
else:
  print(f" a is not equal to b")
```

## Python multiline string
```python
m_string = """
this is a multi
line
string
"""
print(f"Multiline string example: {m_string}")


# adding multiline with fstring format
my_name = "John"
m_string = f"""
this is a multi
line
string
my name {my_name}
"""
print(f"Multiline string example: {m_string}")
```
