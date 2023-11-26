Examples of Python file input and output (I/O) operations:

**Example 1: Writing to a Text File**
```python
# Write a string to a text file
with open("example.txt", "w") as file:
    file.write("Hello, World!")
```

**Example 2: Reading from a Text File**
```python
# Read and print the content of a text file
with open("example.txt", "r") as file:
    content = file.read()
    print(content)
```

**Example 3: Appending to a Text File**
```python
# Append a line to an existing text file
with open("example.txt", "a") as file:
    file.write("\nThis is a new line.")
```

**Example 4: Reading Lines from a Text File**
```python
# Read and print lines from a text file
with open("example.txt", "r") as file:
    lines = file.readlines()
    for line in lines:
        print(line.strip())  # Remove newline characters
```

**Example 5: CSV File Writing and Reading**
```python
import csv

# Writing data to a CSV file
data = [["Name", "Age"], ["Alice", 25], ["Bob", 30]]
with open("data.csv", "w", newline="") as file:
    writer = csv.writer(file)
    writer.writerows(data)

# Reading data from a CSV file
with open("data.csv", "r") as file:
    reader = csv.reader(file)
    for row in reader:
        print(row)
```

**Example 6: JSON File Writing and Reading**
```python
import json

# Writing data to a JSON file
data = {"name": "Alice", "age": 25}
with open("data.json", "w") as file:
    json.dump(data, file)

# Reading data from a JSON file
with open("data.json", "r") as file:
    loaded_data = json.load(file)
    print(loaded_data)
```

**Example 7: Binary File Writing and Reading**
```python
# Writing binary data to a binary file
binary_data = bytes([0x41, 0x42, 0x43, 0x44])
with open("binary_file.bin", "wb") as file:
    file.write(binary_data)

# Reading binary data from a binary file
with open("binary_file.bin", "rb") as file:
    read_data = file.read()
    print(read_data)
```

**Example 8: File Handling with Context Managers**
```python
# Using context managers for file handling
with open("example.txt", "r") as file:
    content = file.read()
    print(content)
# File is automatically closed when the block is exited.
```

**Example 9: Copying Files**
```python
import shutil

# Copy a file to a new location
shutil.copy("example.txt", "example_copy.txt")
```

**Example 10: Deleting a File**
```python
import os

# Delete a file
if os.path.exists("example_copy.txt"):
    os.remove("example_copy.txt")
```

These examples cover various file I/O operations in Python, including reading and writing text files, CSV files, JSON files, binary files, and more.


#Learn the Python File I/O

#### CSV file
```
import csv

# Exercise1: Read a CSV file and print row
with open('./data/file_io/my_data1.csv', 'r') as f:
    reader = csv.reader(f, delimiter=',')
    for row in reader:
        print(row)
        
with open('./data/file_io/my_data1.csv', 'r') as f:
    reader = csv.DictReader(f, delimiter=',')
    for row in reader:
        print(row)

```
#### my_data1.csv
```
ID,Name, LastName, Age, Occupation
1, John, Smith, 40, Engineer
2, Sara, M, 45, Doctor
```

## JSON file
```
import json
from json import JSONDecodeError, JSONEncoder

jsonString = '{"a": "apple", "b": "berry", "c": "cherry",}'
try:
    json.loads(jsonString)
except JSONDecodeError:
    print('Could not parse JSON!')
    
pythonDict = {'a': 'apple', 'b': 'berry', 'c': 'cherry',}
json.dumps(pythonDict)
```
