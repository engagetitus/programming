
# Module 2: Intermediate Programming Concepts

## Lesson 1: Error Handling and Debugging in Python

### Topics
1. Try, Except Blocks
2. Common Errors and Exceptions
3. Debugging Techniques

---

### 1. Try, Except Blocks

#### Overview
Error handling in Python is done through the use of `try` and `except` blocks. This allows developers to handle exceptions (errors) gracefully and maintain the flow of the program.

#### Syntax
```python
try:
    # Code that may cause an exception
    risky_operation()
except SomeException as e:
    # Code that runs if an exception occurs
    handle_exception(e)
finally:
    # Code that always runs, regardless of an exception
    clean_up()
```

#### Example
```python
try:
    file = open('file.txt', 'r')
    content = file.read()
except FileNotFoundError:
    print("The file was not found.")
finally:
    if 'file' in locals():
        file.close()
```

#### Nested Try, Except
```python
try:
    try:
        result = 10 / 0
    except ZeroDivisionError:
        print("Inner: Division by zero.")
except Exception as e:
    print("Outer: An error occurred:", e)
```

---

### 2. Common Errors and Exceptions

#### Overview
Python has several built-in exceptions that handle common errors that can occur during program execution.

#### List of Common Exceptions
- **SyntaxError**: Invalid syntax.
- **TypeError**: Operation applied to an object of inappropriate type.
- **IndexError**: Sequence subscript out of range.
- **KeyError**: Key not found in a dictionary.
- **AttributeError**: Attempt to access an attribute that doesn't exist.
- **ValueError**: Argument of the correct type but inappropriate value.
- **IOError**: I/O operation failed.
- **ZeroDivisionError**: Division by zero.
- **ImportError**: Module not found or couldn't be loaded.

#### Examples
```python
# SyntaxError
try:
    eval('x === 42')
except SyntaxError as e:
    print("Syntax error:", e)

# TypeError
try:
    result = 'a' + 1
except TypeError as e:
    print("Type error:", e)

# IndexError
try:
    lst = [1, 2, 3]
    print(lst[10])
except IndexError as e:
    print("Index error:", e)
```

---

### 3. Debugging Techniques

#### Overview
Debugging is the process of identifying and fixing bugs in your code. Effective debugging techniques help developers find and resolve errors more efficiently.

#### Techniques
- **Print Statements**: Insert print statements to check the flow and state of the program.
- **Using a Debugger**: Tools like pdb, PyCharm, VS Code can help step through the code.
- **Logging**: Use the logging module to record program execution.
- **Code Review**: Having peers review your code can provide fresh insights.
- **Automated Testing**: Writing tests to catch errors early in the development cycle.

#### Examples
```python
# Print Statements
def add(a, b):
    print(f"a: {a}, b: {b}")  # Debugging output
    return a + b

result = add(2, 3)
print("Result:", result)

# Using pdb
import pdb

def add(a, b):
    pdb.set_trace()  # Set a breakpoint
    return a + b

result = add(2, 3)

# Logging
import logging

logging.basicConfig(level=logging.DEBUG)

def add(a, b):
    logging.debug(f"a: {a}, b: {b}")
    return a + b

result = add(2, 3)
logging.info(f"Result: {result}")
```

---

### Conclusion
Error handling and debugging are crucial skills for any programmer. By using `try` and `except` blocks, understanding common errors, and applying effective debugging techniques, you can create more robust and maintainable Python programs.


### List of Common Exceptions

#### SyntaxError: Invalid syntax

A `SyntaxError` occurs when the parser encounters a syntactically incorrect statement.

##### Example 1:
```python
# Missing closing parenthesis
try:
    eval('print("Hello, world!"')
except SyntaxError as e:
    print("Syntax error:", e)
```

##### Example 2:
```python
# Using invalid syntax
try:
    eval('x === 42')
except SyntaxError as e:
    print("Syntax error:", e)
```

#### TypeError: Operation applied to an object of inappropriate type

A `TypeError` occurs when an operation or function is applied to an object of inappropriate type.

##### Example 1:
```python
# Adding string and integer
try:
    result = 'a' + 1
except TypeError as e:
    print("Type error:", e)
```

##### Example 2:
```python
# Calling a function that expects a different type of argument
def add(a, b):
    return a + b

try:
    add(1, 'two')
except TypeError as e:
    print("Type error:", e)
```

#### IndexError: Sequence subscript out of range

An `IndexError` occurs when trying to access an index that is out of the range of a sequence (like a list or a tuple).

##### Example 1:
```python
# Accessing an out-of-range index in a list
try:
    lst = [1, 2, 3]
    print(lst[10])
except IndexError as e:
    print("Index error:", e)
```

##### Example 2:
```python
# Accessing an out-of-range index in a string
try:
    string = "Hello"
    print(string[10])
except IndexError as e:
    print("Index error:", e)
```

#### KeyError: Key not found in a dictionary

A `KeyError` occurs when trying to access a dictionary with a key that does not exist.

##### Example 1:
```python
# Accessing a non-existent key in a dictionary
try:
    d = {'a': 1, 'b': 2}
    print(d['c'])
except KeyError as e:
    print("Key error:", e)
```

##### Example 2:
```python
# Using the get method with a missing key
d = {'a': 1, 'b': 2}
value = d.get('c', 'Key not found')
print(value)  # Outputs: Key not found
```

#### AttributeError: Attempt to access an attribute that doesn't exist

An `AttributeError` occurs when trying to access an attribute of an object that does not exist.

##### Example 1:
```python
# Accessing a non-existent attribute
class MyClass:
    def __init__(self):
        self.name = "MyClass"

obj = MyClass()

try:
    print(obj.age)
except AttributeError as e:
    print("Attribute error:", e)
```

##### Example 2:
```python
# Calling a method that doesn't exist
class MyClass:
    def greet(self):
        print("Hello")

obj = MyClass()

try:
    obj.say_goodbye()
except AttributeError as e:
    print("Attribute error:", e)
```

#### ValueError: Argument of the correct type but inappropriate value

A `ValueError` occurs when a function receives an argument of the correct type but inappropriate value.

##### Example 1:
```python
# Converting an invalid string to an integer
try:
    number = int("not_a_number")
except ValueError as e:
    print("Value error:", e)
```

##### Example 2:
```python
# Using an inappropriate value in a range
try:
    import math
    result = math.sqrt(-1)
except ValueError as e:
    print("Value error:", e)
```

#### IOError: I/O operation failed

An `IOError` occurs when an input/output operation fails. Note that in Python 3, `IOError` has been merged into `OSError`.

##### Example 1:
```python
# Trying to read a non-existent file
try:
    with open('non_existent_file.txt', 'r') as file:
        content = file.read()
except IOError as e:
    print("IO error:", e)
```

##### Example 2:
```python
# Failing to write to a read-only file
try:
    with open('/path/to/read_only_file.txt', 'w') as file:
        file.write("Hello, world!")
except IOError as e:
    print("IO error:", e)
```

#### ZeroDivisionError: Division by zero

A `ZeroDivisionError` occurs when trying to divide a number by zero.

##### Example 1:
```python
# Integer division by zero
try:
    result = 10 / 0
except ZeroDivisionError as e:
    print("ZeroDivision error:", e)
```

##### Example 2:
```python
# Modulo operation with zero
try:
    result = 10 % 0
except ZeroDivisionError as e:
    print("ZeroDivision error:", e)
```

#### ImportError: Module not found or couldn't be loaded

An `ImportError` occurs when an import statement fails to find the module definition or cannot load it.

##### Example 1:
```python
# Importing a non-existent module
try:
    import non_existent_module
except ImportError as e:
    print("Import error:", e)
```

##### Example 2:
```python
# Importing a module from a missing package
try:
    from missing_package import missing_module
except ImportError as e:
    print("Import error:", e)
```

