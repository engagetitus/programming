## Phase 2: Python for Data Science

### Module 2: Machine Learning

#### Lesson 2: Scikit-Learn Basics

---

### Linear Regression

Linear Regression is one of the simplest and most widely used algorithms in machine learning. It is used to model the relationship between a dependent variable (target) and one or more independent variables (features) by fitting a linear equation to the observed data.

#### Key Concepts:
- **Simple Linear Regression**: Models the relationship between two variables by fitting a linear equation to the data.
- **Multiple Linear Regression**: Extends simple linear regression to model the relationship between one dependent variable and multiple independent variables.
- **Equation**: \( y = \beta_0 + \beta_1 x_1 + \beta_2 x_2 + ... + \beta_n x_n \)
  - \( y \): Dependent variable (target)
  - \( x_1, x_2, ..., x_n \): Independent variables (features)
  - \( \beta_0 \): Intercept
  - \( \beta_1, \beta_2, ..., \beta_n \): Coefficients

#### Steps to Perform Linear Regression in Scikit-Learn:
1. **Import the necessary libraries**:
   ```python
   import numpy as np
   from sklearn.model_selection import train_test_split
   from sklearn.linear_model import LinearRegression
   from sklearn.metrics import mean_squared_error, r2_score
   ```

2. **Prepare the data**:
   ```python
   # Sample data
   X = np.array([[1], [2], [3], [4], [5]])
   y = np.array([1, 3, 2, 5, 4])

   # Split the data into training and testing sets
   X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
   ```

3. **Create and train the model**:
   ```python
   model = LinearRegression()
   model.fit(X_train, y_train)
   ```

4. **Make predictions**:
   ```python
   y_pred = model.predict(X_test)
   ```

5. **Evaluate the model**:
   ```python
   mse = mean_squared_error(y_test, y_pred)
   r2 = r2_score(y_test, y_pred)

   print("Mean Squared Error:", mse)
   print("R-squared:", r2)
   ```

#### Example:
```python
import numpy as np
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_squared_error, r2_score

# Sample data
X = np.array([[1], [2], [3], [4], [5]])
y = np.array([1, 3, 2, 5, 4])

# Split the data into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Create and train the model
model = LinearRegression()
model.fit(X_train, y_train)

# Make predictions
y_pred = model.predict(X_test)

# Evaluate the model
mse = mean_squared_error(y_test, y_pred)
r2 = r2_score(y_test, y_pred)

print("Mean Squared Error:", mse)
print("R-squared:", r2)
```

---

### Classification Algorithms

Classification is a supervised learning task where the goal is to predict the categorical class labels of new instances, based on past observations.

#### Common Classification Algorithms:
- **Logistic Regression**: Models the probability of a binary outcome.
- **K-Nearest Neighbors (KNN)**: Classifies instances based on the majority class among the k-nearest neighbors.
- **Support Vector Machines (SVM)**: Finds the hyperplane that best separates classes.
- **Decision Trees**: Splits the data into branches to make decisions.
- **Random Forest**: An ensemble method that uses multiple decision trees to improve classification accuracy.
- **Naive Bayes**: Based on Bayes' theorem, assumes independence between features.

#### Example: Logistic Regression
```python
from sklearn.datasets import load_iris
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LogisticRegression
from sklearn.metrics import accuracy_score, confusion_matrix, classification_report

# Load dataset
iris = load_iris()
X = iris.data
y = iris.target

# Split the data into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Create and train the model
model = LogisticRegression(max_iter=200)
model.fit(X_train, y_train)

# Make predictions
y_pred = model.predict(X_test)

# Evaluate the model
accuracy = accuracy_score(y_test, y_pred)
conf_matrix = confusion_matrix(y_test, y_pred)
class_report = classification_report(y_test, y_pred)

print("Accuracy:", accuracy)
print("Confusion Matrix:\n", conf_matrix)
print("Classification Report:\n", class_report)
```

#### Example: K-Nearest Neighbors (KNN)
```python
from sklearn.datasets import load_iris
from sklearn.model_selection import train_test_split
from sklearn.neighbors import KNeighborsClassifier
from sklearn.metrics import accuracy_score, confusion_matrix, classification_report

# Load dataset
iris = load_iris()
X = iris.data
y = iris.target

# Split the data into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Create and train the model
model = KNeighborsClassifier(n_neighbors=3)
model.fit(X_train, y_train)

# Make predictions
y_pred = model.predict(X_test)

# Evaluate the model
accuracy = accuracy_score(y_test, y_pred)
conf_matrix = confusion_matrix(y_test, y_pred)
class_report = classification_report(y_test, y_pred)

print("Accuracy:", accuracy)
print("Confusion Matrix:\n", conf_matrix)
print("Classification Report:\n", class_report)
```

---

### Model Evaluation

Evaluating a machine learning model is crucial to understand its performance and make improvements. Several metrics and techniques are used to assess the accuracy and reliability of a model.

#### Common Evaluation Metrics:
- **Accuracy**: The proportion of correctly classified instances out of the total instances.
  ```python
  accuracy = accuracy_score(y_test, y_pred)
  ```

- **Confusion Matrix**: A table that describes the performance of a classification model by comparing predicted and actual values.
  ```python
  conf_matrix = confusion_matrix(y_test, y_pred)
  ```

- **Precision**: The proportion of true positive instances out of the instances predicted as positive.
  ```python
  precision = precision_score(y_test, y_pred, average='weighted')
  ```

- **Recall**: The proportion of true positive instances out of the actual positive instances.
  ```python
  recall = recall_score(y_test, y_pred, average='weighted')
  ```

- **F1 Score**: The harmonic mean of precision and recall.
  ```python
  f1 = f1_score(y_test, y_pred, average='weighted')
  ```

- **ROC-AUC**: Receiver Operating Characteristic - Area Under the Curve. Measures the ability of the model to distinguish between classes.
  ```python
  from sklearn.metrics import roc_auc_score
  roc_auc = roc_auc_score(y_test, y_pred, multi_class='ovr')
  ```

#### Example: Model Evaluation
```python
from sklearn.metrics import accuracy_score, confusion_matrix, classification_report, roc_auc_score

# Assume y_test and y_pred are defined

# Accuracy
accuracy = accuracy_score(y_test, y_pred)

# Confusion Matrix
conf_matrix = confusion_matrix(y_test, y_pred)

# Classification Report
class_report = classification_report(y_test, y_pred)

# ROC-AUC Score
roc_auc = roc_auc_score(y_test, y_pred, multi_class='ovr')

print("Accuracy:", accuracy)
print("Confusion Matrix:\n", conf_matrix)
print("Classification Report:\n", class_report)
print("ROC-AUC Score:", roc_auc)
```

---

