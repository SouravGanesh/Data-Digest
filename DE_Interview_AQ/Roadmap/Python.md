## Command Line Arguments in Python:

Python provides access to command-line arguments through the `sys.argv` list or the `argparse` module for more complex argument parsing.

- **Using sys.argv**:
  - `sys.argv`: Contains command-line arguments passed to the script. First argument is the script name.
    ```python
    import sys

    script_name = sys.argv[0]
    arguments = sys.argv[1:]  # Command-line arguments except the script name
    ```

- **Using argparse**:
  - `argparse.ArgumentParser`: Allows structured parsing of command-line arguments. Define arguments, types, help messages, etc.
    ```python
    import argparse

    parser = argparse.ArgumentParser(description='Description of your script.')
    parser.add_argument('arg1', type=int, help='Description of arg1')
    parser.add_argument('--optional_arg', type=str, help='Description of optional_arg')
    args = parser.parse_args()

    # Accessing parsed arguments
    arg1_value = args.arg1
    optional_arg_value = args.optional_arg
    ```
  - Example usage: `python script.py 10 --optional_arg value`


# Regular Expressions (Regex)

Regular expressions, often abbreviated as regex, are a sequence of characters that form a search pattern. They are widely used in various programming languages and text editors to find and manipulate text based on patterns. In Python, the `re` module provides support for regular expressions.

## Understanding Regular Expressions

Regular expressions enable you to search for specific patterns within strings. They allow you to define rules to match characters or sequences of characters in text. For example, you can use regular expressions to find email addresses, phone numbers, or any other structured data within a document.

## Using Special Characters and Metacharacters

Regular expressions utilize special characters and metacharacters to define patterns. Some commonly used special characters include:

- `.` : Matches any single character except newline.
- `^` : Anchors the match to the start of the string.
- `$` : Anchors the match to the end of the string.
- `*` : Matches zero or more occurrences of the preceding character.
- `+` : Matches one or more occurrences of the preceding character.
- `?` : Matches zero or one occurrence of the preceding character.
- `[]` : Matches any single character within the brackets.
- `|` : Acts like a logical OR, matches either the expression before or after the pipe.

These special characters, along with various metacharacters, provide flexibility in defining search patterns.

## Using Regular Expressions in Python

Python's `re` module provides functions to work with regular expressions. Some commonly used functions include `re.search()`, `re.match()`, `re.findall()`, and `re.sub()`.

### Example:

Suppose we want to extract all the email addresses from a given text.

```python
import re

text = "Sample text with email addresses user1@example.com and user2@test.com"
pattern = r'\b[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Z|a-z]{2,}\b'

emails = re.findall(pattern, text)
print(emails)
```

File Input and Output, commonly referred to as file handling, is the process of reading data from and writing data to files on a computer's storage system. This is a fundamental aspect of programming, as it enables applications to store and retrieve data persistently.

Here's a breakdown of the concepts involved:

1. **File Input**: This involves reading data from a file. It typically includes opening the file, reading its contents, processing the data, and then closing the file.

2. **File Output**: This involves writing data to a file. It includes opening a file in write mode, writing data to it, and then closing the file.

Here's a simple example in Python:

```python
# File Input Example
file_path = 'data.txt'
try:
    with open(file_path, 'r') as file:
        data = file.read()
        print("Data read from file:")
        print(data)
except FileNotFoundError:
    print(f"File '{file_path}' not found.")

# File Output Example
output_file_path = 'output.txt'
data_to_write = "This is some data that will be written to the file."

with open(output_file_path, 'w') as file:
    file.write(data_to_write)

print("Data written to file.")
```

In the above example:
- `open()` is used to open a file. The mode `'r'` specifies reading mode, and `'w'` specifies writing mode.
- `with` statement is used for automatic cleanup (closing the file) once the block of code inside it is executed.
- `read()` is used to read the contents of the file.
- `write()` is used to write data to the file.

File handling allows programs to interact with external files, enabling data persistence, data exchange between programs, and storage of program configuration and state. It's an essential skill for any programmer dealing with data storage and manipulation.
