
# Module 2: Intermediate Programming Concepts

## Lesson 3: File Handling in Python

### Topics
1. Reading from Files
2. Writing to Files
3. Working with CSV and JSON Files

---

### 1. Reading from Files

#### Overview
Reading files in Python is done using the built-in `open` function. The `open` function returns a file object, which provides methods and attributes to read data from the file.

#### Reading Text Files
```python
# Open a file for reading
file = open('example.txt', 'r')

# Read the entire file
content = file.read()
print(content)

# Close the file
file.close()
```

#### Reading Line by Line
```python
with open('example.txt', 'r') as file:
    for line in file:
        print(line.strip())  # strip() removes trailing newline characters
```

#### Example File: `example.txt`
```
Hello, world!
Welcome to file handling in Python.
This is the third line.
```

#### Using `readlines`
```python
with open('example.txt', 'r') as file:
    lines = file.readlines()

for line in lines:
    print(line.strip())
```

---

### 2. Writing to Files

#### Overview
Writing to files in Python is also done using the `open` function, but with a different mode (`'w'`, `'a'`, etc.).

#### Writing Text Files
```python
# Open a file for writing
file = open('output.txt', 'w')

# Write to the file
file.write("Hello, world!\n")
file.write("This is a new file.")

# Close the file
file.close()
```

#### Appending to a File
```python
with open('output.txt', 'a') as file:
    file.write("\nAppending a new line.")
```

#### Using `writelines`
```python
lines = ["First line\n", "Second line\n", "Third line\n"]

with open('output.txt', 'w') as file:
    file.writelines(lines)
```

---

### 3. Working with CSV and JSON Files

#### Overview
CSV (Comma-Separated Values) and JSON (JavaScript Object Notation) are common file formats for storing tabular and structured data.

#### Working with CSV Files

##### Reading CSV Files
```python
import csv

with open('data.csv', 'r') as file:
    reader = csv.reader(file)
    for row in reader:
        print(row)
```

##### Writing to CSV Files
```python
import csv

data = [
    ["Name", "Age", "City"],
    ["Charles", 30, "Nairobi"],
    ["Bob", 25, "Kericho"]
]

with open('data.csv', 'w', newline='') as file:
    writer = csv.writer(file)
    writer.writerows(data)
```

#### Working with JSON Files

##### Reading JSON Files
```python
import json

with open('data.json', 'r') as file:
    data = json.load(file)

print(data)
```

##### Writing to JSON Files
```python
import json

data = {
    "name": "Alice",
    "age": 30,
    "city": "New York"
}

with open('data.json', 'w') as file:
    json.dump(data, file, indent=4)
```

---

### Conclusion
File handling is a fundamental skill in Python that allows you to interact with files on your system. Whether you're reading or writing text files, or working with structured data formats like CSV and JSON, mastering these techniques is essential for data manipulation and storage in Python.

---
