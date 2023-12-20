# Python Builtin Collections Module/Classes
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
