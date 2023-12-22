# LinkedLists

LinkedLists are a fundamental data structure in computer science, offering an alternative to 
traditional arrays for storing sequences of data. 
In Python, linked lists can be implemented manually, as Python does not provide a built-in linked list structure like some other languages. Let's go through a simple implementation and explore 10 examples covering 'why', 'what', and 'how' of linked lists in Python.

### 1. Why Use LinkedLists?

**Flexibility in Memory Allocation:**
Unlike arrays, linked lists do not need a contiguous block of memory. Each element (node) contains its data and a reference to the next node, making it suitable for dynamic memory allocation.

**Efficient Insertions/Deletions:**
Inserting or deleting elements in a linked list is more efficient compared to an array, especially for operations at the beginning or in the middle of the list.

### 2. What are LinkedLists?

**Basic Structure:**
A linked list is a sequence of nodes where each node is connected to the next node through a 'next' reference. The first node is called the head, and the last node points to `None`.

**Types of LinkedLists:**
- **Singly Linked List:** Each node has data and a reference to the next node.
- **Doubly Linked List:** Each node has data and two references, one to the next node and one to the previous node.
- **Circular Linked List:** Similar to singly or doubly, but the last node points back to the first node.

### 3. How to Implement LinkedLists?

#### Basic Node Structure
```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None
```

#### Simple LinkedList Implementation
```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class LinkedList:
    def __init__(self):
        self.head = None

    def append(self, data):
        if not self.head:
            self.head = Node(data)
            return
        last = self.head
        while last.next:
            last = last.next
        last.next = Node(data)

    def prepend(self, data):
        new_node = Node(data)
        new_node.next = self.head
        self.head = new_node

    def delete_node(self, key):
        current = self.head
        if current and current.data == key:
            self.head = current.next
            current = None
            return
        prev = None
        while current and current.data != key:
            prev = current
            current = current.next
        if current is None:
            return
        prev.next = current.next
        current = None

    def search(self, key):
        current = self.head
        while current:
            if current.data == key:
                return True
            current = current.next
        return False

    def insert_after_node(self, prev_node, data):
        if not prev_node:
            print("Previous node is not in the list")
            return
        new_node = Node(data)
        new_node.next = prev_node.next
        prev_node.next = new_node

    def delete_list(self):
        current = self.head
        while current:
            prev = current.next
            del current.data
            current = prev
        self.head = None

    def length(self):
        count = 0
        current = self.head
        while current:
            count += 1
            current = current.next
        return count

    def reverse(self):
        prev = None
        current = self.head
        while current:
            nxt = current.next
            current.next = prev
            prev = current
            current = nxt
        self.head = prev

    def has_cycle(self):
        slow = self.head
        fast = self.head
        while fast and fast.next:
            slow = slow.next
            fast = fast.next.next
            if slow == fast:
                return True
        return False

    def merge_sorted(self, llist):
        p = self.head
        q = llist.head
        s = None

        if not p:
            return q
        if not q:
            return p

        if p and q:
            if p.data <= q.data:
                s = p
                p = s.next
            else:
                s = q
                q = s.next
            new_head = s
        while p and q:
            if p.data <= q.data:
                s.next = p
                s = p
                p = s.next
            else:
                s.next = q
                s = q
                q = s.next
        if not p:
            s.next = q
        if not q:
            s.next = p
        return new_head

    def display(self):
        current = self.head
        while current:
            print(current.data, end=" -> ")
            current = current.next
        print("None")

# Usage
llist = LinkedList()
llist.append(10)
llist.append(20)
llist.prepend(5)
llist.insert_after_node(llist.head.next, 15)
llist.display()  # Output: 5 -> 10 -> 15 -> 20 -> None

```



### 10 Examples: Why, What, and How of LinkedLists

#### 1. Creating a LinkedList
```python
llist = LinkedList()
llist.append(10)
llist.append(20)
llist.display()  # Output: 10 -> 20 -> None
```

#### 2. Inserting at the Beginning
```python
def prepend(self, data):
    new_node = Node(data)
    new_node.next = self.head
    self.head = new_node

# Example usage
llist.prepend(5)
llist.display()  # Output: 5 -> 10 -> 20 -> None
```

#### 3. Deleting a Node by Value
```python
def delete_node(self, key):
    current = self.head
    if current and current.data == key:
        self.head = current.next
        current = None
        return
    prev = None
    while current and current.data != key:
        prev = current
        current = current.next
    if current is None:
        return
    prev.next = current.next
    current = None

# Example usage
llist.delete_node(10)
llist.display()  # Output: 5 -> 20 -> None
```

#### 4. Searching in a LinkedList
```python
def search(self, key):
    current = self.head
    while current:
        if current.data == key:
            return True
        current = current.next
    return False

# Example usage
print(llist.search(20))  # Output: True
```

#### 5. Inserting After a Node
```python
def insert_after_node(self, prev_node, data):
    if not prev_node:
        print("Previous node is not in the list")
        return
    new_node = Node(data)
    new_node.next = prev_node.next
    prev_node.next = new_node

# Example usage
llist.insert_after_node(llist.head.next, 15)
llist.display()  # Output: 5 -> 20 -> 15 -> None
```

#### 6. Deleting the Entire LinkedList
```python
def delete_list(self):
    current = self.head
    while current:
        prev = current.next
        del current.data
        current = prev
    self.head = None

# Example usage
llist.delete_list()
llist.display()  # Output: None
```

#### 7. Length of a LinkedList
```python
def length(self):
    count = 0
    current = self.head
    while current:
        count += 1
        current = current.next
    return count

# Example usage
print(llist.length())  # Output: 

3
```

#### 8. Reversing a LinkedList
```python
def reverse(self):
    prev = None
    current = self.head
    while current:
        nxt = current.next
        current.next = prev
        prev = current
        current = nxt
    self.head = prev

# Example usage
llist.reverse()
llist.display()  # Output: 15 -> 20 -> 5 -> None
```

#### 9. Detecting a Loop
A loop in a linked list occurs when a node's next pointer points to an earlier node, creating a cycle. This can be detected using Floyd's cycle-finding algorithm (also known as the tortoise and the hare algorithm).

```python
def has_cycle(self):
    slow = self.head
    fast = self.head
    while fast and fast.next:
        slow = slow.next
        fast = fast.next.next
        if slow == fast:
            return True
    return False
```

#### 10. Merging Two Sorted LinkedLists
This is useful in algorithms like merge sort.

```python
def merge_sorted(self, llist):
    p = self.head
    q = llist.head
    s = None

    if not p:
        return q
    if not q:
        return p

    if p and q:
        if p.data <= q.data:
            s = p
            p = s.next
        else:
            s = q
            q = s.next
        new_head = s
    while p and q:
        if p.data <= q.data:
            s.next = p
            s = p
            p = s.next
        else:
            s.next = q
            s = q
            q = s.next
    if not p:
        s.next = q
    if not q:
        s.next = p
    return new_head
```

These examples provide a basic understanding of how linked lists function in Python and demonstrate their utility in various scenarios. Remember, these implementations are basic and can be extended or modified for more complex applications.
