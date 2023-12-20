# Project1: Duplicate file finder

Creating a duplicate file finder in Python involves a few steps:

1. **Traverse Directories**: Recursively traverse directories to find all files.
2. **Calculate File Hashes**: Calculate a unique hash for each file's content.
3. **Identify Duplicates**: Compare hashes to identify duplicate files.

For hashing, you can use algorithms like SHA-256 which are generally reliable for distinguishing file contents.

Here's a basic structure of how you can implement it:

### Step 1: Traverse Directories and Collect File Paths
You'll need to gather all file paths from the directory you want to scan.

### Step 2: Hashing the Files
For each file, calculate a hash. SHA-256 is a good choice for this.

### Step 3: Identifying Duplicates
Store the hashes and compare them to find duplicates.

### Example Implementation:

```python
import os
import hashlib
import sys
from collections import defaultdict

def hash_file(file_path):
    """ Function to calculate SHA-256 hash of a file """
    hasher = hashlib.sha256()
    with open(file_path, 'rb') as file:
        buf = file.read()
        hasher.update(buf)
    return hasher.hexdigest()

def find_duplicates(directory):
    """ Function to find and return a list of duplicate files """
    files_list = defaultdict(list)

    for root, dirs, files in os.walk(directory):
        for file in files:
            file_path = os.path.join(root, file)
            file_hash = hash_file(file_path)
            files_list[file_hash].append(file_path)

    return [files for hash, files in files_list.items() if len(files) > 1]

def main():
    # Check if a directory path is provided as a command-line argument
    if len(sys.argv) > 1:
        directory_path = sys.argv[1]
    else:
        print("Please provide a directory path.")
        sys.exit(1)

    duplicates = find_duplicates(directory_path)

    # Print duplicate files
    for duplicate_files in duplicates:
        print("Duplicate files:", duplicate_files)

if __name__ == "__main__":
    main()
```

To run this script from the command line, you would use:

```bash
python script_name.py /path/to/directory
```
This script will scan the specified directory, hash each file, and print out the paths of duplicate files. Remember to replace `'your_directory_path'` with the path of the directory you want to scan. 

**Notes**:
- Be cautious with large files as reading them into memory completely (as done in `hash_file` function) might consume a lot of memory. For larger files, consider reading and hashing them in chunks.
- SHA-256 is generally reliable for this purpose, but no hash function is absolutely collision-free in theory.
- This script does not automatically delete or handle duplicates; it only identifies and lists them.

Duplicate file finder program to accept a command-line argument for the directory path, you can use the `sys.argv` feature in Python. 
This allows the program to accept arguments from the command line when the script is executed.

Replace `script_name.py` with the name of your Python script file and `/path/to/directory` with the actual directory path you want to scan.

**Note**:
- The script expects the path as the first argument (`sys.argv[1]`). If no argument is provided, it will prompt the user to provide a directory path and then exit.
- Ensure that you have the necessary permissions to read the files and directories you are scanning.
