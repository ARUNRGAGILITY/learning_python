



## Python pass/by value or reference/is by object
## Immutable: int, float, str, tuples
## Mutable: list, dictionaries, sets

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
