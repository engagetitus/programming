# Module 1: Programming Fundamentals with Python and HTML

## Lesson 6: Data Structures in Python
### Introduction to Data Structures

Data structures are ways to organize and store data so that they can be accessed and modified efficiently. Unlike simple data types (such as `integers`, `floats`, and `strings`) that hold a single value, data structures can hold multiple values and are designed to enable complex data manipulation and management.

### Data structures are essential because they:

- **Organize Data:** They allow us to arrange data in ways that are meaningful and useful.
- **Improve Efficiency:** They help in performing operations like searching, sorting, inserting, and deleting data efficiently.
- **Facilitate Complex Data Handling:** They enable us to handle complex relationships between data, such as hierarchical relationships, sequences, or mappings.

### Why Data Structures are Not Just Data Types

While data types represent the kind of value a variable can hold (e.g., integer, float, string), data structures are more about the organization and manipulation of **collections of data**. Here are some key distinctions:

- **Single Value vs. Multiple Values:** Data types typically hold a single value, whereas data structures can hold multiple values, potentially of different data types.
- **Operations:** Data structures support a variety of operations tailored to the way data is organized (e.g., adding, removing, and accessing elements), whereas operations on simple data types are generally limited to arithmetic or basic manipulation.
- **Purpose:** Data types are fundamental building blocks for variables, whereas data structures provide frameworks for organizing and managing data, often enabling more complex and efficient data manipulation.

### Common Data Structures in Python

In Python, the most common data structures include:

- **Lists**
- **Tuples**
- **Dictionaries**
- **Sets**

We'll explore each of these data structures in detail.
## Lists
Lists are ordered collections of items that are mutable, meaning you can change their content without changing their identity. Lists are created using square brackets `[]`.
```python
# Creating Lists

fruits = ['apple', 'banana', 'cherry']

# Accessing and Modifying List Elements

print(fruits[0])  # Access
fruits[1] = 'blueberry'  # Modify
```
### Common List Methods
- `append()`: Add an element to the end of the list.
- `remove()`: Remove the first matching element from the list.
- `pop()`: Remove and return the last element of the list.
- `sort()`: Sort the list in ascending order.

```python
fruits.append('orange')
fruits.remove('banana')
print(fruits.pop())
fruits.sort()
print(fruits)
```
### List Comprehensions

```python
squares = [x**2 for x in range(10)]
print(squares)
```
## Tuples
Tuples are ordered collections of items that are immutable, meaning once created, their content cannot be changed. Tuples are created using parentheses ().
```python
### Creating Tuples


colors = ('red', 'green', 'blue')

### Accessing Tuple Elements

print(colors[0])
```
## Differences Between Lists and Tuples
- Lists are mutable (can be changed).
- Tuples are immutable (cannot be changed).
### When to Use Tuples
Use tuples for fixed collections of items.

## Dictionaries
Dictionaries are collections of key-value pairs. They are unordered, mutable, and indexed by keys, which are unique within a dictionary. Dictionaries are created using curly braces {}.
```python
### Creating Dictionaries
person = {'name': 'Alice', 'age': 25, 'city': 'New York'}


### Accessing and Modifying Dictionary Elements

print(person['name'])  # Access
person['age'] = 26  # Modify
```
### Common Dictionary Methods
- `keys()`: Return a view of the dictionary's keys.
- `values()`: Return a view of the dictionary's values.
- `items()`: Return a view of the dictionary's key-value pairs.

```python
print(person.keys())
print(person.values())
print(person.items())
```
#### Dictionary Comprehensions

```python
squares = {x: x**2 for x in range(5)}
print(squares)
```
## Sets
Sets are unordered collections of unique items. Sets are mutable and created using curly braces {} or the set() function.
```python
# Creating Sets
numbers = {1, 2, 3, 4, 5}

# Accessing Set Elements
print(numbers)  # Output: {1, 2, 3, 4, 5}

```
Sets are unordered, so you cannot access elements by index.

### Common Set Methods
- `add()`: Add an element to the set.
- `remove()`: Remove an element from the set.
- `union()`: Return the union of sets.
- `intersection()`: Return the intersection of sets.

```
numbers.add(6)
numbers.remove(3)
set1 = {1, 2, 3}
set2 = {3, 4, 5}
print(set1.union(set2))
print(set1.intersection(set2))
```
### Set Operations and Uses
Sets are useful for storing unique items and performing mathematical set operations.

## Tasks
- #### Create and Manipulate a List
Define a list of your favorite movies. Add a new movie to the list, remove one, and sort the list alphabetically.

- #### Work with Tuples
Create a tuple containing the names of five cities. Try changing the name of one city and observe what happens. Explain why tuples are immutable.

- #### Use Dictionaries
Create a dictionary to store information about a book (title, author, year). Add a new key-value pair for the genre, update the year, and remove the author key.

- #### Explore Sets
Create a set of your favorite fruits. Add a new fruit to the set, try adding a duplicate fruit, and remove one fruit. Explain why sets do not allow duplicate items.

- #### Combine Data Structures
Create a list of dictionaries, where each dictionary contains information about a different person (name, age, city). Write a loop to print out the name of each person.

By completing these tasks, you will gain a better understanding of how to define and use different data structures in Python.

### Q&A
Any questions about today's lesson?