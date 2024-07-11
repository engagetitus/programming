## Phase 2: Python for Data Science

### Module 1: Data Analysis with Python

#### Lesson 4: Data Visualization

---

### Introduction to Matplotlib

Matplotlib is a comprehensive library for creating static, animated, and interactive visualizations in Python. It is the foundational plotting library for the Python ecosystem, and many other visualization libraries are built on top of it, including Seaborn.

#### Key Features of Matplotlib:
- **Versatile**: Supports a wide variety of plots and charts (line plots, bar plots, histograms, scatter plots, etc.).
- **Customizable**: Allows extensive customization of plots, including colors, labels, and annotations.
- **Interactive**: Can create interactive plots that can be embedded in web applications.
- **Integration**: Works well with other libraries such as NumPy and Pandas.

#### Basic Structure of a Matplotlib Plot:
1. **Figure**: The overall window or page that everything is drawn on.
2. **Axes**: The area where the data is plotted; a figure can contain multiple axes.
3. **Axis**: Represents the x and y (or z) axis.

#### Creating a Simple Plot:
```python
import matplotlib.pyplot as plt

# Creating data
x = [1, 2, 3, 4, 5]
y = [2, 3, 5, 7, 11]

# Creating a plot
plt.plot(x, y)

# Adding title and labels
plt.title('Simple Line Plot')
plt.xlabel('X Axis')
plt.ylabel('Y Axis')

# Displaying the plot
plt.show()
```

---

### Plotting with Matplotlib

Matplotlib provides a variety of plotting functions and customization options to create different types of visualizations.

#### Line Plot:
```python
plt.plot(x, y, label='Line', color='blue', linewidth=2, linestyle='--')

# Adding title and labels
plt.title('Line Plot')
plt.xlabel('X Axis')
plt.ylabel('Y Axis')

# Adding a legend
plt.legend()

# Displaying the plot
plt.show()
```

#### Bar Plot:
```python
# Creating data
categories = ['A', 'B', 'C', 'D']
values = [3, 7, 5, 4]

# Creating a bar plot
plt.bar(categories, values, color='green')

# Adding title and labels
plt.title('Bar Plot')
plt.xlabel('Categories')
plt.ylabel('Values')

# Displaying the plot
plt.show()
```

#### Histogram:
```python
# Creating data
data = [1, 2, 2, 3, 3, 3, 4, 4, 4, 4, 5, 5, 5, 5, 5]

# Creating a histogram
plt.hist(data, bins=5, color='purple', edgecolor='black')

# Adding title and labels
plt.title('Histogram')
plt.xlabel('Value')
plt.ylabel('Frequency')

# Displaying the plot
plt.show()
```

#### Scatter Plot:
```python
# Creating data
x = [1, 2, 3, 4, 5]
y = [2, 3, 5, 7, 11]

# Creating a scatter plot
plt.scatter(x, y, color='red', marker='o')

# Adding title and labels
plt.title('Scatter Plot')
plt.xlabel('X Axis')
plt.ylabel('Y Axis')

# Displaying the plot
plt.show()
```

#### Customizing Plots:
```python
# Creating data
x = [1, 2, 3, 4, 5]
y = [2, 3, 5, 7, 11]

# Creating a plot with customizations
plt.plot(x, y, color='blue', linewidth=2, linestyle='--', marker='o', markerfacecolor='red', markersize=8)

# Adding grid
plt.grid(True)

# Adding title and labels with font customizations
plt.title('Customized Plot', fontsize=14, fontweight='bold')
plt.xlabel('X Axis', fontsize=12)
plt.ylabel('Y Axis', fontsize=12)

# Displaying the plot
plt.show()
```

---

### Introduction to Seaborn

Seaborn is a Python visualization library based on Matplotlib that provides a high-level interface for drawing attractive and informative statistical graphics. It is particularly well-suited for visualizing complex datasets.

#### Key Features of Seaborn:
- **Beautiful Default Styles**: Offers aesthetically pleasing default themes.
- **Statistical Plotting**: Simplifies the creation of complex plots with built-in statistical aggregations.
- **Integration with Pandas**: Works seamlessly with Pandas DataFrames.
- **Built-in Themes**: Provides several built-in themes for easy customization.

#### Basic Structure of a Seaborn Plot:
```python
import seaborn as sns

# Setting a theme
sns.set_theme(style="darkgrid")

# Loading a sample dataset
tips = sns.load_dataset("tips")

# Creating a basic scatter plot
sns.scatterplot(x="total_bill", y="tip", data=tips)

# Adding title and labels
plt.title('Scatter Plot with Seaborn')
plt.xlabel('Total Bill')
plt.ylabel('Tip')

# Displaying the plot
plt.show()
```

#### Common Plot Types in Seaborn:

##### Scatter Plot:
```python
# Creating a scatter plot
sns.scatterplot(x="total_bill", y="tip", data=tips, hue="time")

# Adding title and labels
plt.title('Scatter Plot with Hue')
plt.xlabel('Total Bill')
plt.ylabel('Tip')

# Displaying the plot
plt.show()
```

##### Line Plot:
```python
# Creating a line plot
sns.lineplot(x="size", y="tip", data=tips)

# Adding title and labels
plt.title('Line Plot')
plt.xlabel('Size')
plt.ylabel('Tip')

# Displaying the plot
plt.show()
```

##### Bar Plot:
```python
# Creating a bar plot
sns.barplot(x="day", y="total_bill", data=tips)

# Adding title and labels
plt.title('Bar Plot')
plt.xlabel('Day')
plt.ylabel('Total Bill')

# Displaying the plot
plt.show()
```

##### Histogram:
```python
# Creating a histogram
sns.histplot(tips["total_bill"], bins=10, kde=True)

# Adding title and labels
plt.title('Histogram with KDE')
plt.xlabel('Total Bill')
plt.ylabel('Frequency')

# Displaying the plot
plt.show()
```

##### Box Plot:
```python
# Creating a box plot
sns.boxplot(x="day", y="total_bill", data=tips)

# Adding title and labels
plt.title('Box Plot')
plt.xlabel('Day')
plt.ylabel('Total Bill')

# Displaying the plot
plt.show()
```

---

