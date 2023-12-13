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

## XML, INI, YAML file i/o

Reading and writing files in different formats like XML, INI, and YAML is a common requirement in many Python applications. Here are examples for each of these file types:

### XML File IO

Python's `xml.etree.ElementTree` module can be used for XML file processing.

#### Reading XML:

```python
import xml.etree.ElementTree as ET

# Reading an XML file
tree = ET.parse('example.xml')
root = tree.getroot()

# Iterating through elements
for child in root:
    print(child.tag, child.attrib)
```

#### Writing XML:

```python
# Creating a new XML file
new_root = ET.Element("data")
item1 = ET.SubElement(new_root, "item")
item1.set("name", "item1")

# Writing to file
tree = ET.ElementTree(new_root)
tree.write("new_example.xml")
```

### INI File IO

For INI files, you can use Python's `configparser` module.

#### Reading INI:

```python
import configparser

config = configparser.ConfigParser()
config.read('example.ini')

# Accessing a specific value
value = config['DEFAULT']['SomeSetting']
print(value)
```

#### Writing INI:

```python
config['DEFAULT'] = {'SomeSetting': 'value', 'AnotherSetting': '10'}

with open('new_example.ini', 'w') as configfile:
    config.write(configfile)
```

### YAML File IO

YAML files can be handled using the `PyYAML` library, which you might need to install first using `pip install PyYAML`.

#### Reading YAML:

```python
import yaml

with open('example.yaml', 'r') as file:
    data = yaml.safe_load(file)
    print(data)
```

#### Writing YAML:

```python
data = {'key': 'value', 'list': [1, 2, 3]}

with open('new_example.yaml', 'w') as file:
    yaml.dump(data, file)
```

In these examples, replace `'example.xml'`, `'example.ini'`, and `'example.yaml'` with the paths to your own files. The reading and writing processes might need to be adjusted based on the specific structure of your files and the data you wish to manipulate. 

For the YAML examples, ensure you have PyYAML installed in your Python environment. If not, you can install it using pip:

```bash
pip install PyYAML
``` 

Remember, working with file IO requires appropriate error handling, especially for production code, to handle situations like missing files, parsing errors, and ensuring file access permissions.
