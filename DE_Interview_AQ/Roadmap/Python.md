# Python Input/Output and Command Line Arguments

This repository provides explanations and examples for Input/Output (I/O) operations and handling Command Line Arguments in Python.

## Input/Output (I/O) in Python:

Python offers built-in functions and methods for input and output operations:

- **Input (stdin)**:
  - `input(prompt)`: Allows user input from the keyboard. It takes an optional prompt and returns a string.

- **Output (stdout)**:
  - `print(*objects, sep=' ', end='\n', file=sys.stdout, flush=False)`: Prints objects to the standard output (console). 

- **File I/O**:
  - Reading from a file: `with open('filename.txt', 'r') as file: data = file.read()`
  - Writing to a file: `with open('filename.txt', 'w') as file: file.write("Hello, World!")`

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
