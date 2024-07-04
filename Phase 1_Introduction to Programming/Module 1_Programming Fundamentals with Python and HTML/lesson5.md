# Module 1: Programming Fundamentals with Python and HTML

## Lesson 4: Functions and Modules in Python

## Defining Functions

### Introduction to Functions
Functions are **reusable blocks of code** that perform a specific task. 
- They help to break down complex problems into simpler parts and make the code more organized and manageable.

### Syntax of a Function
```python
def function_name():
    # Function body
    return value
```
#### Examples of Simple Functions
```python
def greet(name):
    return f"Hello, {name}!"

print(greet("Alice"))
```
## Importance of Functions in Programming
- Promote code reuse
- Enhance readability
- Facilitate debugging and maintenance
- Allow for modular design and development
## Function Parameters and Return Values

### Function Parameters
Parameters are variables that you define in the function signature to accept values when the function is called. They act as placeholders for the values that will be passed to the function.

```python
## syntax with parameters

def function_name(parameters):
    # Function body
    return value

## example

def greet(name):
    print(f"Hello, {name}!")

print(greet("Jane"))
```
In the above example, `name` is a parameter of the `greet` function.

### Positional and Keyword Arguments
### Positional Arguments
Positional arguments are arguments that need to be included in the correct order in which the parameters were defined.

```python
def describe_pet(animal_type, pet_name):
    print(f"I have a {animal_type} named {pet_name}.")

# Calling the function with positional arguments
describe_pet('hamster', 'Harry')
In this example, 'hamster' is assigned to animal_type and 'Harry' is assigned to pet_name because of their positions.

Keyword Arguments
Keyword arguments are arguments that are passed to a function by explicitly stating the parameter names. This allows you to pass the arguments in any order.

python
Copy code
# Calling the function with keyword arguments
describe_pet(pet_name='Harry', animal_type='hamster')
```
In this example, pet_name is explicitly set to `Harry` and animal_type is set to `hamster`, regardless of their positions.

### Keyword Arguments
Keyword arguments are arguments that are passed to a function by explicitly stating the parameter names. This allows you to pass the arguments in any order.

```python
# Calling the function with keyword arguments
describe_pet(pet_name='Harry', animal_type='hamster')
```
In this example, pet_name is explicitly set to 'Harry' and animal_type is set to 'hamster', regardless of their positions.

### Combining Positional and Keyword Arguments
You can use both positional and keyword arguments in a single function call. However, positional arguments **must** come before keyword arguments.

``` python

describe_pet('hamster', pet_name='Harry')
```
### Default Parameter Values
You can define default values for parameters. If an argument is not provided for a parameter with a default value, the default value is used.

```python
def describe_pet(pet_name, animal_type='dog'):
    print(f"I have a {animal_type} named {pet_name}.")

# Calling the function without specifying the animal_type
describe_pet('Willie')
```
In this example, animal_type defaults to `dog` if it is not provided in the function call.

### Variable-Length Arguments (*args and **kwargs)
Sometimes, you might want to define a function that accepts a variable number of arguments.

#### *args
The *args parameter allows you to pass a variable number of positional arguments to a function.

```python
def make_pizza(size, *toppings):
    print(f"Making a {size}-inch pizza with the following toppings:")
    for topping in toppings:
        print(f"- {topping}")

make_pizza(12, 'pepperoni', 'mushrooms', 'green peppers')
```
In this example, *toppings collects all additional positional arguments into a tuple.

#### **kwargs
The **kwargs parameter allows you to pass a variable number of keyword arguments to a function.

```python

def build_profile(first, last, **user_info):
    profile = {}
    profile['first_name'] = first
    profile['last_name'] = last
    for key, value in user_info.items():
        profile[key] = value
    return profile

user_profile = build_profile('albert', 'einstein', location='princeton', field='physics')

print(user_profile)
```
In this example, **user_info collects all additional keyword arguments into a dictionary.

### Return Values
The return statement is used to send a value back to the caller of the function. A function can return any type of data, including numbers, strings, lists, dictionaries, or even other functions.

```python

def add(a, b):
    return a + b

result = add(3, 5)
print(result)  # Output: 8
```
In this example, the add function returns the sum of a and b, which is then stored in the variable result and printed.

## Importing and Using Modules
### What are Modules? 📦
Modules are files containing Python code, which can include functions, classes, and variables. They help to organize and reuse code.

### The `import` Statement
```python
import math
print(math.sqrt(16))
```
### Using Standard Library Modules
```python
import random
print(random.randint(1, 10))
```

### Creating and Importing Custom Modules
- Create a file named `mymodule.py`:
```python
# mymodule.py
def greet(name):
    return f"Hello, {name}!"
```
- Import and use the custom module:
```python
import mymodule
print(mymodule.greet("Alice"))
```

