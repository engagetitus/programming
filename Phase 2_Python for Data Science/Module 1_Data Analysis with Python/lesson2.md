## Phase 2: Python for Data Science

### Module 1: Data Analysis with Python

#### Lesson 2: NumPy for Numerical Data

---

### NumPy Arrays

NumPy (Numerical Python) is a powerful library for numerical computing in Python. It provides support for arrays, matrices, and many mathematical functions to operate on these data structures.

#### Key Features of NumPy Arrays:
- **N-dimensional arrays**: The core object is the ndarray, an N-dimensional array.
- **Element-wise operations**: Supports element-wise operations and broadcasting.
- **Efficient storage and computation**: Memory-efficient and faster computations compared to Python lists.
- **Extensive functions**: Provides numerous functions for mathematical, logical, shape manipulation, sorting, and more.

#### Creating NumPy Arrays:
```python
import numpy as np

# Creating a 1D array
arr1 = np.array([1, 2, 3, 4, 5])

# Creating a 2D array
arr2 = np.array([[1, 2, 3], [4, 5, 6]])

# Creating an array of zeros
zeros = np.zeros((3, 3))

# Creating an array of ones
ones = np.ones((2, 4))

# Creating an array with a range of values
range_array = np.arange(0, 10, 2)

# Creating an array with random values
random_array = np.random.rand(3, 3)
```

#### Array Attributes:
- `ndim`: Number of dimensions.
- `shape`: Dimensions of the array.
- `size`: Total number of elements.
- `dtype`: Data type of elements.

```python
print(arr2.ndim)  # Output: 2
print(arr2.shape)  # Output: (2, 3)
print(arr2.size)  # Output: 6
print(arr2.dtype)  # Output: int64
```

---

### Basic Operations with NumPy

NumPy provides a range of mathematical and statistical operations that can be performed on arrays.

#### Arithmetic Operations:
```python
arr1 = np.array([1, 2, 3, 4])
arr2 = np.array([5, 6, 7, 8])

# Element-wise addition
sum_arr = arr1 + arr2

# Element-wise subtraction
diff_arr = arr1 - arr2

# Element-wise multiplication
prod_arr = arr1 * arr2

# Element-wise division
div_arr = arr1 / arr2
```

#### Aggregate Functions:
```python
arr = np.array([1, 2, 3, 4, 5])

# Sum of all elements
total_sum = np.sum(arr)

# Mean of all elements
mean_val = np.mean(arr)

# Standard deviation
std_dev = np.std(arr)

# Minimum and maximum values
min_val = np.min(arr)
max_val = np.max(arr)
```

#### Linear Algebra Operations:
```python
matrix1 = np.array([[1, 2], [3, 4]])
matrix2 = np.array([[5, 6], [7, 8]])

# Matrix multiplication
matrix_prod = np.dot(matrix1, matrix2)

# Transpose of a matrix
matrix_transpose = np.transpose(matrix1)

# Inverse of a matrix
matrix_inverse = np.linalg.inv(matrix1)
```

---

### Indexing, Slicing, and Iterating

NumPy arrays can be indexed, sliced, and iterated over similarly to Python lists, but with additional features for multi-dimensional arrays.

#### Indexing:
```python
arr = np.array([1, 2, 3, 4, 5])

# Accessing a single element
element = arr[2]  # Output: 3

# Accessing elements in a 2D array
arr2d = np.array([[1, 2, 3], [4, 5, 6]])
element_2d = arr2d[1, 2]  # Output: 6
```

#### Slicing:
```python
arr = np.array([1, 2, 3, 4, 5])

# Slicing elements
slice_arr = arr[1:4]  # Output: [2, 3, 4]

# Slicing in a 2D array
arr2d = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])
slice_2d = arr2d[0:2, 1:3]  # Output: [[2, 3], [5, 6]]
```

#### Iterating:
```python
arr = np.array([1, 2, 3, 4, 5])

# Iterating over a 1D array
for element in arr:
    print(element)

# Iterating over a 2D array
arr2d = np.array([[1, 2, 3], [4, 5, 6]])
for row in arr2d:
    for element in row:
        print(element)
```

#### Boolean Indexing:
```python
arr = np.array([1, 2, 3, 4, 5])

# Boolean indexing
bool_idx = arr > 3
filtered_arr = arr[bool_idx]  # Output: [4, 5]
```

---

