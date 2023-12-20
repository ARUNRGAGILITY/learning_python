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


# Project2: Reading Excel file

To read an Excel file and summarize data based on date and expense amount, you can use the `pandas` library in Python, which is a powerful tool for data manipulation and analysis. Here's a step-by-step guide:

### Step 1: Install Pandas and Openpyxl
First, ensure you have `pandas` and `openpyxl` installed, as `openpyxl` is needed for reading Excel files (.xlsx). You can install them via pip if you haven't already:

```bash
pip install pandas openpyxl
```

### Step 2: Read the Excel File
Use `pandas` to read the Excel file. Assume your Excel file has columns named "Date" and "Expense Amount".

### Step 3: Summarize Data
Group the data by date and sum up the expense amounts for each date.

### Example Code:

```python
import pandas as pd

def summarize_expenses(file_path):
    # Read the Excel file
    df = pd.read_excel(file_path)

    # Ensure the date column is in datetime format
    df['Date'] = pd.to_datetime(df['Date'])

    # Summarize expense by date
    summary = df.groupby(df['Date']).sum()

    return summary

# Replace 'your_file.xlsx' with your Excel file path
summary = summarize_expenses('your_file.xlsx')
print(summary)
```

#### excel file contents
|    Date    | Expense Amount |
|------------|----------------|
| 2023-01-01 |           150  |
| 2023-01-01 |           200  |
| 2023-01-02 |           100  |
| 2023-01-03 |           250  |


This script will read the Excel file, group the expenses by date, and print the sum of expenses for each date.

**Note:**
- Replace `'your_file.xlsx'` with the actual path to your Excel file.
- Ensure your Excel file has the columns "Date" and "Expense Amount". The names should match exactly, or you'll need to adjust the column names in the script accordingly.
- This script assumes that the "Date" column is in a recognizable date format. If your dates are in a different format, you might need to parse them accordingly using `pd.to_datetime` with the appropriate format string.
- If your Excel file has headers in the first row, `pandas` will automatically use them. If not, you can specify headers using the `header` parameter in `pd.read_excel`.
