# Concurrency and parallelism
Concurrency and parallelism are techniques used in computer science to improve the efficiency of executing tasks, especially when dealing with large datasets or performing multiple operations simultaneously. While they serve similar purposes, they operate differently and are suitable for different scenarios.

1. **Concurrency**:
   - Concurrency refers to the ability of a system to handle multiple tasks at the same time, seemingly simultaneously. However, in reality, the tasks may not run simultaneously but are interleaved by the system.
   - Concurrency is achieved through techniques such as multitasking, where multiple tasks are executed in overlapping time periods, or through asynchronous programming, where tasks are initiated without waiting for the previous task to complete.
   - In Python, concurrency is often achieved using threading and asynchronous programming.

2. **Parallelism**:
   - Parallelism, on the other hand, involves actually executing multiple tasks simultaneously, typically by utilizing multiple processing units or cores.
   - Parallelism can lead to more significant performance improvements compared to concurrency but may require more resources.
   - In Python, parallelism is achieved using multiprocessing.

Now, let's explore how these concepts are implemented in Python:

- **Threading**: Threading involves running multiple threads of execution within a single process. Threads share the same memory space and can communicate directly with each other.
  ```python
  import threading

  def print_numbers():
      for i in range(5):
          print(threading.current_thread().name, i)

  # Create two threads
  thread1 = threading.Thread(target=print_numbers)
  thread2 = threading.Thread(target=print_numbers)

  # Start the threads
  thread1.start()
  thread2.start()

  # Wait for threads to finish
  thread1.join()
  thread2.join()
  ```

- **Multiprocessing**: Multiprocessing involves running multiple processes in parallel, each with its memory space. This allows for true parallelism and can utilize multiple CPU cores effectively.
  ```python
  import multiprocessing

  def print_numbers():
      for i in range(5):
          print(multiprocessing.current_process().name, i)

  # Create two processes
  process1 = multiprocessing.Process(target=print_numbers)
  process2 = multiprocessing.Process(target=print_numbers)

  # Start the processes
  process1.start()
  process2.start()

  # Wait for processes to finish
  process1.join()
  process2.join()
  ```

- **Asynchronous Programming**: Asynchronous programming allows tasks to be executed concurrently without blocking other tasks. It is particularly useful for I/O-bound operations where tasks spend most of their time waiting for external resources.
  ```python
  import asyncio

  async def print_numbers():
      for i in range(5):
          print(i)
          await asyncio.sleep(1)  # Simulate asynchronous I/O

  asyncio.run(print_numbers())
  ```

In addition to the standard library modules like `threading`, `multiprocessing`, and `asyncio`, Python also provides higher-level abstractions like `concurrent.futures` and `asyncio` to simplify concurrent and parallel programming tasks. Understanding these concepts and libraries can significantly improve the performance and scalability of Python applications, especially when dealing with computationally intensive or I/O-bound tasks.

# Functional programming
Functional programming is a programming paradigm that emphasizes the use of functions as the primary building blocks of software. In functional programming, functions are treated as first-class citizens, meaning they can be passed around as arguments to other functions, returned as values from other functions, and assigned to variables.

In Python, functional programming features are supported, allowing you to write code in a functional style. Here's an explanation of some key concepts and features:

1. **Lambda Functions**: Lambda functions, also known as anonymous functions, are functions that are defined without a name. They are typically used for short, one-line functions where a full function definition is not necessary. Lambda functions are created using the `lambda` keyword.

   Example:
   ```python
   # Lambda function to square a number
   square = lambda x: x ** 2
   print(square(5))  # Output: 25
   ```

2. **Map, Filter, and Reduce**: These are built-in higher-order functions in Python that are commonly used in functional programming.

   - **Map**: The `map()` function applies a given function to each item of an iterable (e.g., a list) and returns a new iterable with the results.
   
     Example:
     ```python
     # Using map to double each number in a list
     numbers = [1, 2, 3, 4, 5]
     doubled = list(map(lambda x: x * 2, numbers))
     print(doubled)  # Output: [2, 4, 6, 8, 10]
     ```

   - **Filter**: The `filter()` function constructs an iterator from elements of an iterable for which a function returns true.
   
     Example:
     ```python
     # Using filter to get even numbers from a list
     numbers = [1, 2, 3, 4, 5]
     evens = list(filter(lambda x: x % 2 == 0, numbers))
     print(evens)  # Output: [2, 4]
     ```

   - **Reduce**: The `reduce()` function is used to apply a function of two arguments cumulatively to the items of an iterable, from left to right, to reduce the iterable to a single value.
   
     Example:
     ```python
     from functools import reduce
     # Using reduce to calculate the sum of a list
     numbers = [1, 2, 3, 4, 5]
     total = reduce(lambda x, y: x + y, numbers)
     print(total)  # Output: 15
     ```

3. **Comprehensions**: Comprehensions provide a concise way to create lists, dictionaries, and sets in Python.

   Example:
   ```python
   # List comprehension to create a list of squares
   squares = [x ** 2 for x in range(1, 6)]
   print(squares)  # Output: [1, 4, 9, 16, 25]
   ```

Functional programming promotes code that is easier to understand, test, and maintain by focusing on pure functions, immutability, and avoiding side effects. By leveraging features like lambda functions, map, filter, reduce, and comprehensions, you can write more expressive and efficient code in Python.

# Command Line Arguments in Python:

Python provides access to command-line arguments through the `sys.argv` list or the `argparse` module for more complex argument parsing.

- **Using sys.argv**:
  Command-line arguments are parameters passed to a program when it is executed via the command line interface (CLI). These arguments provide a way to customize the behavior of a program without modifying its source code. In many programming languages, including Python, you can access these arguments within your program and use them to perform specific tasks or configurations.

In Python, the `sys.argv` list in the `sys` module is commonly used to access command-line arguments. The first element (`sys.argv[0]`) contains the name of the script being executed, and subsequent elements contain the arguments passed to the script.

Here's an example demonstrating how to access and use command-line arguments in Python:

```python
import sys

# Check the number of command-line arguments
if len(sys.argv) < 2:
    print("Usage: python script.py <arg1> <arg2> ...")
    sys.exit(1)  # Exit with an error code

# Accessing command-line arguments
script_name = sys.argv[0]
args = sys.argv[1:]

print("Script name:", script_name)
print("Arguments:", args)

# Example usage: Concatenating command-line arguments
result = ' '.join(args)
print("Concatenated arguments:", result)
```

Let's assume this script is named `script.py`. Here's how you would run it from the command line and pass arguments:

```
$ python script.py arg1 arg2 arg3
```

In this example:
- `sys.argv[0]` would be `"script.py"`.
- `sys.argv[1:]` would be `["arg1", "arg2", "arg3"]`.

You can use these arguments within your Python script to perform various tasks. Common use cases include configuration, file paths, options, or any other parameters that your program might need to operate effectively.

Command-line arguments provide a convenient way to interact with your programs without needing to modify the source code each time you want to change its behavior, making your programs more flexible and adaptable.

- **Using argparse**:
Using `argparse` is a more sophisticated way to handle command-line arguments in Python. It's a standard module in the Python Standard Library that provides a powerful and flexible mechanism for parsing command-line arguments and generating help messages. `argparse` makes it easy to define the structure of the command-line interface for your program and automatically handles parsing, validation, and error reporting.

Here's a basic example of how to use `argparse`:

```python
import argparse

# Create ArgumentParser object
parser = argparse.ArgumentParser(description='A simple program to demonstrate argparse.')

# Add arguments
parser.add_argument('name', help='Name of the user')
parser.add_argument('--age', type=int, help='Age of the user')

# Parse the command-line arguments
args = parser.parse_args()

# Accessing the arguments
name = args.name
age = args.age

print("Hello,", name)
if age:
    print("You are", age, "years old.")
else:
    print("Your age is not provided.")
```

In this example:
- We import the `argparse` module.
- We create an `ArgumentParser` object, `parser`, with a description.
- We add arguments using `add_argument()` method. The first argument is positional (`name`), and the second one is optional (`--age`).
- We parse the command-line arguments using `parse_args()` method, which returns an object containing the argument values.
- We access the argument values using dot notation (`args.name`, `args.age`).

Now, if you run this script from the command line:

```bash
$ python script.py John --age 30
```

It will print:

```
Hello, John
You are 30 years old.
```

`argparse` automatically handles parsing and validation of the arguments, including checking whether required arguments are provided and converting argument values to the specified data types (`int` in the case of `--age`).

`argparse` also provides support for generating help messages and handling various types of arguments, such as flags, positional arguments, and sub-commands. It's a powerful tool for building robust and user-friendly command-line interfaces for your Python programs.


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

# Exception handling
Exception handling in programming is a mechanism to deal with unexpected or exceptional situations that may occur during the execution of a program. These situations, often called exceptions, can arise due to various reasons such as invalid input, file not found, network errors, or division by zero. Exception handling allows the program to gracefully handle such errors, preventing the program from crashing and providing the opportunity to recover or handle the error appropriately.

In Python, exception handling is done using the `try`, `except`, `else`, and `finally` blocks. Here's how they work:

1. **try**: The code that might raise an exception is placed inside the `try` block.

2. **except**: If an exception occurs inside the `try` block, the code inside the corresponding `except` block is executed. You can specify which type of exception you want to catch, or catch all exceptions by using `except Exception`.

3. **else**: The code inside the `else` block is executed if no exceptions occur in the `try` block.

4. **finally**: The code inside the `finally` block is always executed, regardless of whether an exception occurred or not. It is typically used for cleanup tasks like closing files or releasing resources.

Here's an example demonstrating the use of exception handling in Python:

```python
try:
    # Code that might raise an exception
    x = int(input("Enter a number: "))
    result = 10 / x
    print("Result:", result)

except ValueError:
    print("Invalid input! Please enter a valid number.")
    
except ZeroDivisionError:
    print("Error: Division by zero!")

else:
    print("No exceptions occurred.")

finally:
    print("Finally block executed. This code always runs.")

print("Program continues...")
```

In the above example:
- If the user enters a non-numeric value, a `ValueError` exception is raised and caught by the first `except` block.
- If the user enters zero, a `ZeroDivisionError` exception is raised and caught by the second `except` block.
- If the user enters a valid number and no exceptions occur, the `else` block is executed.
- Regardless of whether an exception occurred or not, the `finally` block is executed.

Exception handling helps make your code more robust and resilient to errors, improving the overall reliability of your software. It's essential to handle exceptions appropriately to provide a good user experience and prevent unexpected crashes.