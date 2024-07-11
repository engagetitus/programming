
# Module 2: Intermediate Programming Concepts

## Lesson 4: Libraries and Frameworks in Python

### Topics
1. Introduction to Popular Python Libraries
2. Using Pip for Package Management

---

### 1. Introduction to Popular Python Libraries

#### Overview
Python has a rich ecosystem of libraries and frameworks that enhance its capabilities and make it suitable for a wide range of applications.

## Popular Libraries

### NumPy
NumPy is a library for numerical computations. It provides support for arrays and matrices, along with a collection of mathematical functions to operate on them.

```python
import numpy as np

# Creating an array
arr = np.array([1, 2, 3, 4, 5])
print(arr)

# Performing mathematical operations
print(arr + 10)
print(np.mean(arr))
```

### Pandas
Pandas is a library for data manipulation and analysis. It provides data structures like DataFrame and Series, which are essential for handling tabular data.

```python
import pandas as pd

# Creating a DataFrame
data = {
    "Name": ["John", "Bob", "Charlie"],
    "Age": [25, 30, 35],
    "City": ["Mombasa", "Kisumu", "Nanyuki"]
}
df = pd.DataFrame(data)
print(df)

# DataFrame operations
print(df.describe())
print(df[df["Age"] > 30])
```

### Matplotlib
Matplotlib is a plotting library for creating static, animated, and interactive visualizations in Python.

```python
import matplotlib.pyplot as plt

# Creating a simple plot
x = [1, 2, 3, 4, 5]
y = [2, 3, 5, 7, 11]

plt.plot(x, y)
plt.title("Simple Plot")
plt.xlabel("X-axis")
plt.ylabel("Y-axis")
plt.show()
```

##### Flask
Flask is a lightweight web framework for building web applications. It is easy to use and provides the necessary tools to create web applications quickly.

```python
from flask import Flask

app = Flask(__name__)

@app.route('/')
def home():
    return "Hello, Flask!"

if __name__ == "__main__":
    app.run(debug=True)
```

### Requests
Requests is a simple and elegant HTTP library for making API calls and handling HTTP requests.

```python
import requests

# Making a GET request
response = requests.get('https://api.coding.titus.co.ke')
print(response.status_code)
print(response.json())
```

---

## 2. Using Pip for Package Management

### Overview
Pip is the package installer for Python. It allows you to install and manage additional libraries and dependencies that are not distributed as part of the standard library.

### Installing Pip
Pip is usually installed with Python. You can check if pip is installed by running:
```sh
pip --version
```

If pip is not installed, you can download and install it from:
[https://pip.pypa.io/en/stable/installation/](https://pip.pypa.io/en/stable/installation/)

#### Basic Pip Commands

##### Installing a Package
```sh
pip install package_name
```
Example:
```sh
pip install requests
```

##### Installing a Specific Version
```sh
pip install package_name==version
```
Example:
```sh
pip install requests==2.25.1
```

##### Upgrading a Package
```sh
pip install --upgrade package_name
```
Example:
```sh
pip install --upgrade requests
```

##### Listing Installed Packages
```sh
pip list
```

##### Uninstalling a Package
```sh
pip uninstall package_name
```
Example:
```sh
pip uninstall requests
```

##### Using Requirements Files
Requirements files allow you to specify a list of packages to be installed together.
Create a `requirements.txt` file with the following content:
```
requests==2.11.1
flask==3.0.3
```
Install all packages listed in the file:
```sh
pip install -r requirements.txt
```

---

### Conclusion
Understanding and utilizing Python's vast ecosystem of libraries and frameworks is crucial for efficient development. Using pip for package management ensures that you can easily install, update, and manage the dependencies required for your projects.

---
