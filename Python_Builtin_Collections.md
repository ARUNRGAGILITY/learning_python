# Python Builtin Collections Module/Classes

Python `collections` module:

1. Counters
2. DefaultDict
3. OrderedDict
4. ChainMap
5. NamedTuple
6. DeQue
7. UserList
8. UserString
9. UserDict



1. **Counter**
   - **Purpose**: Counting occurrences of elements.
   - **Practical Use Case**: Analyzing the frequency of items in a list can be useful for statistics, such as finding the most common words in a document.

   ```python
   # Find the three most common words in a text
   words = "apple banana apple strawberry banana lemon apple banana".split()
   word_counts = Counter(words)
   most_common_three = word_counts.most_common(3)
   print(most_common_three)  # Output: [('apple', 3), ('banana', 3), ('strawberry', 1)]
   ```

2. **defaultdict**
   - **Purpose**: Assigning default values to keys that do not exist.
   - **Practical Use Case**: Grouping items without having to initialize a list for new keys, such as categorizing a list of tuples into a dictionary.

   ```python
   # Group animals by their type
   animal_list = [('dog', 'Fido'), ('cat', 'Whiskers'), ('dog', 'Clifford'), ('parrot', 'Polly')]
   animal_dict = defaultdict(list)
   for animal, name in animal_list:
       animal_dict[animal].append(name)
   print(animal_dict)  # Output: defaultdict(<class 'list'>, {'dog': ['Fido', 'Clifford'], 'cat': ['Whiskers'], 'parrot': ['Polly']})
   ```

3. **OrderedDict**
   - **Purpose**: Maintaining the order of keys.
   - **Practical Use Case**: When the order of entries is critical, such as in an ordered configuration file where parameters have a specific sequence.

   ```python
   # Remember the order of tasks completed
   tasks_completed = OrderedDict()
   tasks_completed['wake up'] = '7am'
   tasks_completed['breakfast'] = '8am'
   tasks_completed['work'] = '9am'
   for task, time in tasks_completed.items():
       print(f"Task: {task}, Time: {time}")
   ```

4. **ChainMap**
   - **Purpose**: Searching through multiple dictionaries as one.
   - **Practical Use Case**: For an application with multiple configuration settings, `ChainMap` can be used to define a priority: user settings override defaults.

   ```python
   # Application settings: defaults and overrides
   default_settings = {'color': 'blue', 'font': 'Arial'}
   user_settings = {'font': 'Tahoma'}
   settings = ChainMap(user_settings, default_settings)
   print(settings['color'], settings['font'])  # Output: blue Tahoma
   ```

5. **namedtuple**
   - **Purpose**: Lightweight, immutable data structures with named fields.
   - **Practical Use Case**: Reading a CSV file where each row represents a record with fields, and accessing the fields by name improves code readability.

   ```python
   # Employee records
   Employee = namedtuple('Employee', 'name, age, department')
   emp1 = Employee('John Doe', 30, 'Finance')
   print(emp1)  # Output: Employee(name='John Doe', age=30, department='Finance')
   ```

6. **deque**
   - **Purpose**: Efficient appends and pops from either end.
   - **Practical Use Case**: Implementing a queue for tasks in a multi-threaded environment since it’s thread-safe.

   ```python
   # Maintaining a fixed-size queue of the latest N items
   recent_items = deque(maxlen=5)
   for i in range(10):
       recent_items.append(i)
       print(f"New item: {i}, Recent 5: {list(recent_items)}")
   ```

7. **UserList**
   - **Purpose**: Easier list subclassing.
   - **Practical Use Case**: Creating a custom list type that has certain constraints, like a typed array or a list that does not allow duplicates.

   ```python
   # A list that only accepts integers and no duplicates
   class IntegerSet(UserList):
       def append(self, item):
           if not isinstance(item, int):
               raise TypeError("Only integers are allowed")
           if item not in self.data:
               super().append(item)
   ```

8. **UserString**
   - **Purpose**: Easier string subclassing.
   - **Practical Use Case**: Extending string functionality, such as adding methods for specific kinds of parsing or formatting.

   ```python
   # A custom string class that adds a method to reverse the string
   class MyString(UserString):
       def reverse(self):
           return self.data[::-1]
   ```

9. **UserDict**
   - **Purpose**: Easier dict subclassing.


   - **Practical Use Case**: Extending the dictionary to provide additional methods or to enforce certain rules on keys or values.

   ```python
   # A dictionary that never allows deletion of items
   class PersistentDict(UserDict):
       def __delitem__(self, key):
           raise NotImplementedError("Item deletion not allowed")
   ```

These examples show how each class can be used in a meaningful context, demonstrating their practical applications in various programming scenarios.


# Python Built-in Classes explaination

 `collections` classes with an explanation and example:

1. **Counter**
   - A `Counter` is a `dict` subclass for counting hashable objects. It is a collection where elements are stored as dictionary keys and their counts are stored as dictionary values.

   ```python
   from collections import Counter

   # Count the frequency of each character in a string
   c = Counter('hello world')
   print(c)  # Counter({'l': 3, 'o': 2, 'h': 1, 'e': 1, ' ': 1, 'w': 1, 'r': 1, 'd': 1})
   ```

2. **defaultdict**
   - The `defaultdict` is a `dict` subclass that calls a factory function to supply missing values.

   ```python
   from collections import defaultdict

   # Function that returns a default value for the missing keys
   def default_value():
       return "Not Present"
   
   d = defaultdict(default_value)
   d['a'] = 1
   d['b'] = 2
   print(d['a'])  # Output: 1
   print(d['c'])  # Output: Not Present
   ```

3. **OrderedDict**
   - An `OrderedDict` is a `dict` subclass that remembers the order that keys were first inserted.

   ```python
   from collections import OrderedDict

   # Remember the order the keys are added to the dictionary
   od = OrderedDict()
   od['a'] = 1
   od['b'] = 2
   od['c'] = 3
   for key in od:
       print(key, od[key])
   ```

4. **ChainMap**
   - A `ChainMap` groups multiple dictionaries into a single view.

   ```python
   from collections import ChainMap

   # Combine two dictionaries for a single view
   dict1 = {'a': 1, 'b': 2}
   dict2 = {'b': 3, 'c': 4}
   cm = ChainMap(dict1, dict2)
   print(cm['b'])  # Output: 2 (values from the first dictionary have precedence)
   ```

5. **namedtuple**
   - `namedtuple` creates tuple-like objects that have fields accessible by attribute lookup as well as being indexable and iterable.

   ```python
   from collections import namedtuple

   # Create a namedtuple to represent a point in 2D space
   Point = namedtuple('Point', ['x', 'y'])
   p = Point(11, y=22)
   print(p[0] + p[1])  # Output: 33
   print(p.x + p.y)    # Output: 33
   ```

6. **deque**
   - A `deque` is a list optimized for inserting and removing items.

   ```python
   from collections import deque

   # Initialize a deque with three items
   d = deque('abc')
   d.append('d')         # add to the right
   d.appendleft('z')     # add to the left
   print(d)  # Output: deque(['z', 'a', 'b', 'c', 'd'])
   ```

7. **UserList**
   - `UserList` is a wrapper around list objects for easier list subclassing.

   ```python
   from collections import UserList

   # Create a subclass of UserList
   class MyList(UserList):
       def append(self, item):
           if not isinstance(item, int):
               raise ValueError("Only integers are allowed")
           super().append(item)
   
   ml = MyList([1, 2, 3])
   ml.append(4)
   print(ml)  # Output: [1, 2, 3, 4]
   ```

8. **UserString**
   - `UserString` is a wrapper around string objects for easier string subclassing.

   ```python
   from collections import UserString

   # Create a subclass of UserString
   class MyString(UserString):
       def append(self, s):
           self.data += s
   
   ms = MyString("Python")
   ms.append("3.8")
   print(ms)  # Output: Python3.8
   ```

9. **UserDict**
   - `UserDict` is a wrapper around dictionary objects for easier dict subclassing.

   ```python
   from collections import UserDict

   # Create a subclass of UserDict
   class MyDict(UserDict):
       def pop(self, key):
           raise NotImplementedError("Pop is not allowed for MyDict")
   
   md = MyDict({'a': 1, 'b': 2})
   print(md)  # Output: {'a': 1, 'b': 2}
