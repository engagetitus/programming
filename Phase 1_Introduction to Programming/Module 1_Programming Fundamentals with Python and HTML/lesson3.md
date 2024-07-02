# Module 1: Programming Fundamentals with Python and HTML

## Lesson 3: Control Structures in Python

### Objectives
- Understand control structures in Python
- Learn about conditional statements
- Learn about loops
### Control Structures in Python

#### What are Control Structures?
Control structures are blocks of programming code that analyze variables and choose directions in which to go based on given parameters. 
- They enable the flow of control in a program to be changed or controlled, which is essential for creating dynamic and complex functionalities.

## Types of Control Structures
There are three main types of control structures in programming:

1. **Sequential Control**
2. **Selection Control**
3. **Repetition Control**

### Sequential Control
This is the default mode where the instructions are executed one after the other in the order they appear.

### Selection Control
Selection control structures allow a program to execute certain parts of code based on conditions. Python supports several types of selection control structures:
- **if Statement**: Executes a block of code if a specified condition is true.
- **if-else Statement**: Executes one block of code if a condition is true, and another block of code if it is false.
- **if-elif-else Statement**: Allows multiple conditions to be checked sequentially.

### Repetition Control
Repetition control structures (or loops) allow a block of code to be executed repeatedly based on a condition. Python supports two main types of loops:

- for Loop: Iterates over a sequence (such as a list, tuple, string, or range).
- while Loop: Repeats a block of code as long as a specified condition is true.

### Conditional Statements
- `if`, `elif`, and `else` statements are used to perform different actions based on different conditions

#### Example
```python
age = 18

if age < 18:
    print("You are a minor.")
elif age == 18:
    print("You just became an adult.")
else:
    print("You are an adult.")
```
### Loops
for and while loops are used to repeat a block of code
#### For Loop
```
for i in range(5):
    print(i)
```

### While Loop
```
count = 0

while count < 5:
    print(count)
    count += 1
```

## Break and Continue
- `break` is used to exit a loop prematurely
- `continue` is used to skip the rest of the code inside the loop for the current iteration and continue with the next iteration

### Example
```
for i in range(10):
    if i == 5:
        break
    print(i)

for i in range(10):
    if i % 2 == 0:
        continue
    print(i)
```
### Task
- Write a Python program that prints the first 10 numbers in the Fibonacci sequence
- Create a Python script that asks the user for a number and prints whether it's prime or not
### Q&A
Any questions about today's lesson?