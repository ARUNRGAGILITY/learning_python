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

### YAML Tutorials

### What is YAML?

YAML, which stands for "YAML Ain't Markup Language" (a recursive acronym), is a human-readable data serialization format. It is commonly used for configuration files and data exchange between languages with different data structures. The format is broadly recognized for its ease of use and readability, especially in comparison to other data formats like XML or JSON.

### Features of YAML

1. **Human-Readable**: YAML's syntax is designed to be easily readable by humans. It uses indentation (spaces) to represent hierarchy, making it visually clear and straightforward.

2. **Cross-Language Support**: YAML is language-independent and can be used with any programming language that has a YAML library, such as Python, Ruby, Perl, PHP, and Java.

3. **Data Serialization**: YAML can represent scalars (like strings, integers, floats), lists (arrays), and associative arrays (dictionaries or maps).

4. **No Closing Tags**: Unlike XML, YAML doesn’t use closing tags, which reduces clutter and improves readability.

5. **Support for Complex Data Types**: YAML supports complex data types, including nested lists and dictionaries, which can be very useful for configuring complex applications.

### Why is YAML Used?

1. **Configuration Files**: Due to its readability and simplicity, YAML is often used for writing configuration files in development projects. It's particularly popular in environments like Docker, Kubernetes, and various Continuous Integration (CI) systems.

2. **Data Exchange**: YAML can be used for exchanging data between different programming environments, providing a way to serialize and share complex data structures.

3. **Infrastructure as Code (IaC)**: In modern DevOps practices, YAML is frequently used for defining and managing infrastructure, as seen in tools like Ansible, Terraform, and in Kubernetes manifests.

### Example of a YAML File

Here's a simple example to illustrate YAML’s syntax:

```yaml
# Sample YAML content
person:
  name: John Doe
  age: 30
  married: true
  children:
    - name: Jane Doe
      age: 10
    - name: Jack Doe
      age: 8
addresses:
  home:
    street: 123 Main St
    city: Anytown
  office:
    street: 456 Elm St
    city: Somewhere
```

In this example, you can see a mix of key-value pairs, lists, and nested dictionaries, showcasing how YAML can represent complex data structures in a readable format.

#### Explaination of the format
In YAML, the colon `:` and the hyphen `-` are used to define the structure and elements of the data. Understanding their usage is key to correctly interpreting and writing YAML files.

### The Colon `:` - Key-Value Pairs

In YAML, a colon `:` followed by a space is used to assign a value to a key, creating a key-value pair. This is similar to dictionaries in Python or objects in JSON. Here's how it works:

- **Syntax**: `key: value`
- **Purpose**: To define a property (key) and assign a value to it.
- **Example**:
  ```yaml
  name: John Doe
  age: 30
  ```

In this example, `name` and `age` are keys, and `John Doe` and `30` are their respective values.

### The Hyphen `-` - List Elements

The hyphen `-` is used to define elements of a list. In YAML, lists are collections of items, similar to arrays in other programming languages. Each item in a list is preceded by a hyphen and a space.

- **Syntax**: 
  ```yaml
  - item1
  - item2
  ```
- **Purpose**: To create a list where each item is a value in the list.
- **Example**:
  ```yaml
  children:
    - name: Jane Doe
      age: 10
    - name: Jack Doe
      age: 8
  ```

Here, `children` is a key, and its value is a list of items, each representing a child with their `name` and `age`. The hyphen `-` indicates the start of a new item in the list.

### Combined Example

Let's look at a combined example:

```yaml
person:
  name: John Doe
  age: 30
  children:
    - name: Jane Doe
      age: 10
    - name: Jack Doe
      age: 8
```

- `person` is a key with a dictionary as its value.
- Inside `person`, `name` and `age` are keys with `John Doe` and `30` as their respective values.
- `children` is a key whose value is a list, indicated by elements starting with `-`.
- Each item in the `children` list is a dictionary with keys `name` and `age`.

Understanding these symbols and their usage is crucial for working with YAML files, as they define the structure and relationships of the data.


### Conclusion

YAML's popularity stems from its straightforward syntax, human readability, and its ability to handle complex data structures elegantly. 
This makes it an ideal choice for configuration files, data storage, and data exchange in a variety of applications and programming environments.
