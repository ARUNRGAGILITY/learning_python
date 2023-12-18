

## Examples of Data Structures
Let's go through examples of each of the mentioned data structures and algorithms in Python. 
These examples will give you a practical understanding of how they are implemented and used.

### 1. Arrays

Arrays in Python are typically implemented using lists. Here's a simple example:

```python
# Creating an array (list in Python)
array = [1, 2, 3, 4, 5]

# Accessing elements
print("Element at index 2:", array[2])

# Modifying an element
array[2] = 10
print("Modified array:", array)
```

### 2. Linked Lists

A basic implementation of a singly linked list:

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class LinkedList:
    def __init__(self):
        self.head = None

    def printList(self):
        temp = self.head
        while temp:
            print(temp.data, end=' ')
            temp = temp.next

# Example usage
llist = LinkedList()
llist.head = Node(1)
second = Node(2)
third = Node(3)

llist.head.next = second
second.next = third

llist.printList()
```

### 3. Trees

Implementing a simple binary tree:

```python
class Node:
    def __init__(self, key):
        self.left = None
        self.right = None
        self.val = key

# Example usage
root = Node(1)
root.left = Node(2)
root.right = Node(3)

root.left.left = Node(4)
root.left.right = Node(5)
```

### 4. Graphs

Representing a graph using an adjacency list:

```python
class Graph:
    def __init__(self):
        self.graph = {}

    def add_edge(self, u, v):
        if u in self.graph:
            self.graph[u].append(v)
        else:
            self.graph[u] = [v]

# Example usage
g = Graph()
g.add_edge(0, 1)
g.add_edge(0, 2)
g.add_edge(1, 2)
g.add_edge(2, 0)
g.add_edge(2, 3)
g.add_edge(3, 3)

print(g.graph)
```

### 5. Sorting Algorithms

Example of Bubble Sort:

```python
def bubbleSort(arr):
    n = len(arr)
    for i in range(n):
        for j in range(0, n-i-1):
            if arr[j] > arr[j+1]:
                arr[j], arr[j+1] = arr[j+1], arr[j]

# Example usage
arr = [64, 34, 25, 12, 22, 11, 90]
bubbleSort(arr)
print("Sorted array is:", arr)
```

### 6. Searching Algorithms

Example of Binary Search:

```python
def binarySearch(arr, l, r, x):
    if r >= l:
        mid = l + (r - l) // 2
        if arr[mid] == x:
            return mid
        elif arr[mid] > x:
            return binarySearch(arr, l, mid-1, x)
        else:
            return binarySearch(arr, mid + 1, r, x)
    else:
        return -1

# Example usage
arr = [2, 3, 4, 10, 40]
x = 10
result = binarySearch(arr, 0, len(arr)-1, x)
print("Element is present at index", result)
```

### 7. Dynamic Programming

Example of Fibonacci Series using Dynamic Programming:

```python
def fibonacci(n, memo={}):
    if n in memo:
        return memo[n]
    if n <= 2:
        return 1
    memo[n] = fibonacci(n - 1, memo) + fibonacci(n - 2, memo)
    return memo[n]

# Example usage
print(fibonacci(10))
```
