## Phase 2: Python for Data Science

### Module 2: Machine Learning

#### Lesson 3: Advanced Machine Learning Concepts

---

### Decision Trees and Random Forests

#### Decision Trees

Decision Trees are versatile and powerful supervised learning algorithms used for both classification and regression tasks. They work by recursively partitioning the data into subsets based on the most significant feature at each node.

##### Key Concepts:
- **Nodes**: Represent a feature or a decision point.
- **Edges**: Represent the outcome of a split based on a feature.
- **Root Node**: The topmost node that splits the data.
- **Leaf Node**: Terminal nodes that predict the outcome.

##### Example:
```python
from sklearn.datasets import load_iris
from sklearn.model_selection import train_test_split
from sklearn.tree import DecisionTreeClassifier
from sklearn.metrics import accuracy_score, confusion_matrix, classification_report

# Load dataset
iris = load_iris()
X = iris.data
y = iris.target

# Split the data into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Create and train the model
model = DecisionTreeClassifier()
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

#### Random Forests

Random Forests are an ensemble learning method that constructs multiple decision trees during training and outputs the mode of the classes (classification) or average prediction (regression) of the individual trees.

##### Key Concepts:
- **Ensemble Learning**: Combines multiple models to improve performance and robustness.
- **Bagging**: Bootstrap Aggregating, a technique to reduce variance by averaging multiple models.
- **Random Feature Selection**: Each tree in the forest is trained on a subset of features.

##### Example:
```python
from sklearn.ensemble import RandomForestClassifier
from sklearn.datasets import load_iris
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score, confusion_matrix, classification_report

# Load dataset
iris = load_iris()
X = iris.data
y = iris.target

# Split the data into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Create and train the model
model = RandomForestClassifier(n_estimators=100, random_state=42)
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

### Clustering Algorithms

Clustering is an unsupervised learning technique that groups similar data points into clusters. It is used to discover the inherent structure within the data.

#### Common Clustering Algorithms:
- **K-Means**: Divides data into k clusters based on centroid similarity.
- **Hierarchical Clustering**: Builds a tree of clusters.
- **DBSCAN (Density-Based Spatial Clustering of Applications with Noise)**: Clusters data points together based on density.

#### Example: K-Means Clustering
```python
from sklearn.cluster import KMeans
from sklearn.datasets import make_blobs
import matplotlib.pyplot as plt

# Generate sample data
X, _ = make_blobs(n_samples=300, centers=4, cluster_std=0.60, random_state=0)

# Create the model
kmeans = KMeans(n_clusters=4)
kmeans.fit(X)

# Predict the clusters
y_kmeans = kmeans.predict(X)

# Plotting the clusters
plt.scatter(X[:, 0], X[:, 1], c=y_kmeans, s=50, cmap='viridis')

# Plotting centroids
centers = kmeans.cluster_centers_
plt.scatter(centers[:, 0], centers[:, 1], c='red', s=200, alpha=0.75)

plt.title('K-Means Clustering')
plt.xlabel('Feature 1')
plt.ylabel('Feature 2')
plt.show()
```

---

### Neural Networks (Basic Introduction)

Neural Networks are a class of algorithms inspired by the human brain's structure and function. They are capable of learning complex patterns from data and are widely used in various machine learning tasks.

#### Key Concepts:
- **Neurons**: Basic units that receive inputs and produce outputs.
- **Layers**: Neurons are organized into layers (input, hidden, output).
- **Activation Function**: Determines the output of a neuron.
- **Weights and Biases**: Adjusted during training to minimize error.
- **Backpropagation**: Algorithm used to train neural networks by adjusting weights based on error.

#### Example: Simple Neural Network with Keras (TensorFlow Backend)
```python
import numpy as np
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import Dense

# Sample data
X = np.array([[0, 0], [0, 1], [1, 0], [1, 1]])
y = np.array([[0], [1], [1], [0]])

# Create the model
model = Sequential([
    Dense(4, input_dim=2, activation='relu'),
    Dense(1, activation='sigmoid')
])

# Compile the model
model.compile(loss='binary_crossentropy', optimizer='adam', metrics=['accuracy'])

# Train the model
model.fit(X, y, epochs=100, batch_size=1, verbose=1)

# Evaluate the model
loss, accuracy = model.evaluate(X, y)
print(f"Loss: {loss:.4f}, Accuracy: {accuracy:.4f}")

# Make predictions
predictions = model.predict(X)
print("Predictions:\n", predictions)
```

---
