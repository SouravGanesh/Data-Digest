# Command Line Arguments in Python:

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
Regular expressions (regex) in Python are powerful tools for pattern matching and manipulation of strings. They provide a concise and flexible means for identifying patterns within text data. Python's `re` module provides support for working with regular expressions.

Here's an overview of the key components of regular expressions in Python:

1. **Literal Characters**: Regular expressions can consist of literal characters (e.g., 'a', 'b', 'c') which match themselves in the input string.

2. **Metacharacters**: Metacharacters are special characters in regular expressions that carry a specific meaning. Some common metacharacters include:
   - `.` : Matches any single character except newline.
   - `^` : Matches the start of a string.
   - `$` : Matches the end of a string.
   - `*` : Matches zero or more occurrences of the preceding character.
   - `+` : Matches one or more occurrences of the preceding character.
   - `?` : Matches zero or one occurrence of the preceding character.
   - `[]` : Matches any single character within the brackets.
   - `()` : Groups patterns together.

3. **Quantifiers**: Quantifiers specify how many occurrences of a character or group should be matched. For example, `*` matches zero or more occurrences, `+` matches one or more occurrences, `?` matches zero or one occurrence.

4. **Character Classes**: Character classes allow you to match a specific set of characters. For example, `[a-z]` matches any lowercase letter.

5. **Anchors**: Anchors specify positions in the input string. `^` matches the beginning of a string, and `$` matches the end of a string.

6. **Escaping**: Backslash `\` is used to escape metacharacters if you want to match them literally.

Here's a simple example demonstrating the usage of regular expressions in Python:

```python
import re

# Example 1: Matching a pattern
pattern = r'apple'
text = 'I like to eat an apple every day.'
match = re.search(pattern, text)
if match:
    print("Pattern found:", match.group())
else:
    print("Pattern not found.")

# Example 2: Using quantifiers
pattern = r'\d+'  # Matches one or more digits
text = 'My phone number is 123-456-7890.'
match = re.search(pattern, text)
if match:
    print("Phone number found:", match.group())
else:
    print("Phone number not found.")

# Example 3: Using character classes
pattern = r'[aeiou]'  # Matches any vowel
text = 'Hello, how are you today?'
matches = re.findall(pattern, text)
print("Vowels found:", matches)
```

In the examples above:
- `re.search()` searches for the first occurrence of the pattern in the text.
- `re.findall()` finds all occurrences of the pattern in the text.
- `r''` is used to denote raw strings in Python, which is recommended for regular expressions to avoid unintended escape sequences.

Regular expressions are incredibly versatile and can be used for tasks such as validating input, extracting data, and text manipulation. However, they can also be complex, so it's essential to understand their syntax and behavior.
### Example:

Suppose we want to extract all the email addresses from a given text.

```python
import re

text = "Sample text with email addresses user1@example.com and user2@test.com"
pattern = r'\b[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Z|a-z]{2,}\b'

emails = re.findall(pattern, text)
print(emails)
```

# File handling
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
