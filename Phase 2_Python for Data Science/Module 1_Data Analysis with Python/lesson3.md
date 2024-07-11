## Phase 2: Python for Data Science

### Module 1: Data Analysis with Python

#### Lesson 3: Pandas for Data Manipulation

---

### Pandas DataFrames

Pandas is a powerful and flexible open-source data analysis and manipulation library for Python. It provides data structures and functions needed to work with structured data seamlessly. The primary data structures in Pandas are `Series` and `DataFrame`.

#### Key Features of Pandas DataFrames:
- **DataFrame**: A 2-dimensional labeled data structure with columns of potentially different types.
- **Indexing**: Label-based and integer-based indexing.
- **Data Alignment**: Automatic and explicit data alignment, handling missing data.
- **Group By**: Perform split-apply-combine operations on datasets.
- **Reshaping**: Pivoting and stacking data.

#### Creating Pandas DataFrames:
```python
import pandas as pd

# Creating a DataFrame from a dictionary
data = {
    'Name': ['Alice', 'Bob', 'Charlie'],
    'Age': [25, 30, 35],
    'City': ['New York', 'Los Angeles', 'Chicago']
}
df = pd.DataFrame(data)

# Creating a DataFrame from a list of dictionaries
data = [
    {'Name': 'Alice', 'Age': 25, 'City': 'New York'},
    {'Name': 'Bob', 'Age': 30, 'City': 'Los Angeles'},
    {'Name': 'Charlie', 'Age': 35, 'City': 'Chicago'}
]
df = pd.DataFrame(data)

# Creating a DataFrame from a CSV file
df = pd.read_csv('data.csv')
```

#### DataFrame Attributes:
- `shape`: Dimensions of the DataFrame.
- `columns`: Column labels.
- `index`: Row labels.

```python
print(df.shape)  # Output: (3, 3)
print(df.columns)  # Output: Index(['Name', 'Age', 'City'], dtype='object')
print(df.index)  # Output: RangeIndex(start=0, stop=3, step=1)
```

#### Accessing Data:
- **Selecting Columns**: `df['column_name']` or `df.column_name`.
- **Selecting Rows**: `df.loc[]` for label-based indexing and `df.iloc[]` for integer-based indexing.

```python
# Selecting a column
ages = df['Age']

# Selecting multiple columns
subset = df[['Name', 'City']]

# Selecting a row by label
row = df.loc[0]

# Selecting a row by integer position
row = df.iloc[1]

# Selecting a subset of rows and columns
subset = df.loc[0:1, ['Name', 'City']]
```

---

### Data Cleaning

Data cleaning is the process of preparing raw data for analysis by removing or correcting errors and inconsistencies. It involves handling missing values, removing duplicates, and correcting data types.

#### Handling Missing Values:
- **Identifying Missing Values**: `df.isnull()` or `df.isna()`.
- **Filling Missing Values**: `df.fillna()`.
- **Dropping Missing Values**: `df.dropna()`.

```python
# Identifying missing values
missing_values = df.isnull().sum()

# Filling missing values with a specific value
df['Age'].fillna(df['Age'].mean(), inplace=True)

# Dropping rows with missing values
df.dropna(inplace=True)
```

#### Removing Duplicates:
- **Identifying Duplicates**: `df.duplicated()`.
- **Dropping Duplicates**: `df.drop_duplicates()`.

```python
# Identifying duplicate rows
duplicates = df.duplicated()

# Dropping duplicate rows
df.drop_duplicates(inplace=True)
```

#### Correcting Data Types:
- **Converting Data Types**: `df['column_name'].astype()`.
- **Parsing Dates**: `pd.to_datetime()`.

```python
# Converting a column to integer
df['Age'] = df['Age'].astype(int)

# Parsing a date column
df['Date'] = pd.to_datetime(df['Date'])
```

---

### Data Transformation

Data transformation involves changing the format, structure, or values of data to make it suitable for analysis. Common transformations include normalization, scaling, and encoding categorical variables.

#### Normalization and Scaling:
- **Normalization**: Rescaling data to a range of [0, 1].
- **Standardization**: Rescaling data to have a mean of 0 and a standard deviation of 1.

```python
from sklearn.preprocessing import MinMaxScaler, StandardScaler

# Normalizing data
scaler = MinMaxScaler()
df['Normalized_Age'] = scaler.fit_transform(df[['Age']])

# Standardizing data
scaler = StandardScaler()
df['Standardized_Age'] = scaler.fit_transform(df[['Age']])
```

#### Encoding Categorical Variables:
- **Label Encoding**: Assigning a unique integer to each category.
- **One-Hot Encoding**: Creating binary columns for each category.

```python
from sklearn.preprocessing import LabelEncoder, OneHotEncoder

# Label encoding
label_encoder = LabelEncoder()
df['City_Label'] = label_encoder.fit_transform(df['City'])

# One-hot encoding
one_hot_encoder = OneHotEncoder()
city_encoded = one_hot_encoder.fit_transform(df[['City']]).toarray()
df = pd.concat([df, pd.DataFrame(city_encoded, columns=one_hot_encoder.categories_)], axis=1)
```

#### Applying Functions:
- **Using `apply()`**: Apply a function along an axis of the DataFrame.
- **Using `applymap()`**: Apply a function element-wise to the DataFrame.

```python
# Applying a function to a column
df['Age_plus_10'] = df['Age'].apply(lambda x: x + 10)

# Applying a function element-wise
df = df.applymap(lambda x: x*2 if isinstance(x, (int, float)) else x)
```

---

### Merging and Joining DataFrames

Merging and joining are methods used to combine multiple DataFrames into a single DataFrame. Pandas provides several functions to perform these operations, such as `merge()`, `join()`, and `concat()`.

#### Merging DataFrames:
- **Inner Join**: Returns only the common rows in both DataFrames.
- **Outer Join**: Returns all rows from both DataFrames, with NaNs where they don't match.
- **Left Join**: Returns all rows from the left DataFrame, and matching rows from the right DataFrame.
- **Right Join**: Returns all rows from the right DataFrame, and matching rows from the left DataFrame.

```python
df1 = pd.DataFrame({'key': ['A', 'B', 'C'], 'value1': [1, 2, 3]})
df2 = pd.DataFrame({'key': ['B', 'C', 'D'], 'value2': [4, 5, 6]})

# Inner join
inner_join = pd.merge(df1, df2, on='key', how='inner')

# Outer join
outer_join = pd.merge(df1, df2, on='key', how='outer')

# Left join
left_join = pd.merge(df1, df2, on='key', how='left')

# Right join
right_join = pd.merge(df1, df2, on='key', how='right')
```

#### Joining DataFrames:
- **Joining on Index**: Combines DataFrames based on their index.

```python
df1 = pd.DataFrame({'value1': [1, 2, 3]}, index=['A', 'B', 'C'])
df2 = pd.DataFrame({'value2': [4, 5, 6]}, index=['B', 'C', 'D'])

# Join
joined_df = df1.join(df2, how='inner')
```

#### Concatenating DataFrames:
- **Concatenating Along Rows**: Stack DataFrames vertically.
- **Concatenating Along Columns**: Stack DataFrames horizontally.

```python
df1 = pd.DataFrame({'A': [1, 2, 3]})
df2 = pd.DataFrame({'B': [4, 5, 6]})

# Concatenating along rows
concat_rows = pd.concat([df1, df2], axis=0)

# Concatenating along columns
concat_columns = pd.concat([df1, df2], axis=1)
```

---
