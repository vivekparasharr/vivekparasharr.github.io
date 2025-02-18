---
title: "Implementing Artificial Neural Networks using Python"
date: "2022-03-05"
tags:
    - deep-learning
    - artificial-neural-network
    - ann
    - scikit-learn
    - tensorflow
    - keras
    - pytorch
thumbnail: "/assets/img/placeholder.jpg"
---
## What are Artificial Neural Networks (ANNs)? 
Artificial Neural Networks (ANNs) are a type of machine learning model that are designed to simulate the function of a biological neural network. ANNs are composed of interconnected nodes or artificial neurons that process and transmit information to one another. The structure of an ANN consists of an input layer, one or more hidden layers, and an output layer.

The input layer is where data is introduced to the network, while the output layer produces the network’s prediction or classification. Hidden layers contain a variable number of artificial neurons, which allow the network to model non-linear relationships in the data. The connections between the neurons in the hidden layers have weights that can be adjusted through training to optimize the performance of the network.

ANNs can be used for a variety of machine learning tasks, including regression, classification, and clustering. For regression, ANNs can be trained to model the relationship between input variables and output variables. In classification, ANNs can be trained to classify input data into different categories. In clustering, ANNs can be used to group similar data points together.

The training process of an ANN involves adjusting the weights of the connections between the neurons to minimize the difference between the predicted output and the actual output. This process involves passing data through the network multiple times and updating the weights based on the difference between the predicted output and the actual output. The goal is to find a set of weights that minimize the error and optimize the performance of the network.

---

## Implementation
Python has several libraries that can be used to implement ANNs, including scikit-learn, TensorFlow, Keras, and PyTorch. These libraries provide high-level abstractions that make it easier to build and train ANNs. In addition, they provide a wide range of pre-built layers and functions that can be used to customize the architecture of the network.

### Using scikit-learn library
Here's an example of how to create a simple ANN using the scikit-learn library:

```python
# Import the necessary libraries
from sklearn.neural_network import MLPClassifier
from sklearn.datasets import make_classification
from sklearn.model_selection import train_test_split

# Generate a random dataset for classification
X, y = make_classification(n_features=4, random_state=0)

# Split the data into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, y, stratify=y, random_state=0)

# Create an ANN classifier with one hidden layer
clf = MLPClassifier(hidden_layer_sizes=(5,), max_iter=1000, random_state=0)

# Train the classifier on the training set
clf.fit(X_train, y_train)

# Evaluate the classifier on the testing set
score = clf.score(X_test, y_test)
print("Accuracy: {:.2f}%".format(score*100))
```

In this example, we first import the necessary libraries, generate a random dataset for classification, and split the data into training and testing sets. We then create an ANN classifier with one hidden layer and train it on the training set. Finally, we evaluate the classifier on the testing set and print the accuracy.

This is just a basic example, and there are many ways to customize and optimize your ANN, depending on your specific use case.

---

### Using Tensorflow library
Here's an example of how to implement an artificial neural network using TensorFlow without Keras:

```python
import tensorflow as tf
import numpy as np

# Define the input data and expected outputs
input_data = np.array([[0,0], [0,1], [1,0], [1,1]], dtype=np.float32)
expected_output = np.array([[0], [1], [1], [0]], dtype=np.float32)

# Define the network architecture
num_input = 2
num_hidden = 2
num_output = 1
learning_rate = 0.1

# Define the weights and biases for the network
weights = {
    'hidden': tf.Variable(tf.random.normal([num_input, num_hidden])),
    'output': tf.Variable(tf.random.normal([num_hidden, num_output]))
}
biases = {
    'hidden': tf.Variable(tf.random.normal([num_hidden])),
    'output': tf.Variable(tf.random.normal([num_output]))
}

# Define the forward propagation step
def neural_network(input_data):
    hidden_layer = tf.add(tf.matmul(input_data, weights['hidden']), biases['hidden'])
    hidden_layer = tf.nn.sigmoid(hidden_layer)
    output_layer = tf.add(tf.matmul(hidden_layer, weights['output']), biases['output'])
    output_layer = tf.nn.sigmoid(output_layer)
    return output_layer

# Define the loss function and optimizer
loss_func = tf.keras.losses.MeanSquaredError()
optimizer = tf.keras.optimizers.SGD(learning_rate=learning_rate)

# Define the training loop
num_epochs = 10000
for epoch in range(num_epochs):
    with tf.GradientTape() as tape:
        # Forward propagation
        output = neural_network(input_data)
        loss = loss_func(expected_output, output)
    # Backward propagation and update the weights and biases
    gradients = tape.gradient(loss, [weights['hidden'], weights['output'], biases['hidden'], biases['output']])
    optimizer.apply_gradients(zip(gradients, [weights['hidden'], weights['output'], biases['hidden'], biases['output']]))
    if epoch % 1000 == 0:
        print(f"Epoch {epoch} Loss: {loss:.4f}")

# Test the network
test_data = np.array([[0,0], [0,1], [1,0], [1,1]], dtype=np.float32)
predictions = neural_network(test_data)
print(predictions)
```

In this example, we define the architecture of the neural network by specifying the number of input, hidden, and output nodes. We also define the learning rate and the weight and bias variables. The forward propagation step is defined by using the tf.add() and tf.matmul() functions to compute the weighted sum and then applying the sigmoid activation function. The loss function and optimizer are defined using the tf.keras.losses and tf.keras.optimizers modules, respectively. Finally, we train the network by performing forward and backward propagation steps in a loop, and then we test the network using test data.

---

### Using keras library
Keras is a high-level neural network API that can run on top of TensorFlow. It provides a simplified interface for building and training deep learning models. Here is an example of how to implement an Artificial Neural Network (ANN) in Python using Keras:

```python
# Import the necessary libraries
from tensorflow import keras
from tensorflow.keras import layers

# Define the model architecture
model = keras.Sequential([
    layers.Dense(64, activation='relu', input_shape=[X_train.shape[1]]),
    layers.Dense(64, activation='relu'),
    layers.Dense(1, activation='sigmoid')
])

# Compile the model
model.compile(
    optimizer='adam',
    loss='binary_crossentropy',
    metrics=['accuracy']
)

# Train the model
history = model.fit(
    X_train, y_train,
    validation_data=(X_val, y_val),
    epochs=100,
    batch_size=32
)

# Evaluate the model
test_scores = model.evaluate(X_test, y_test, verbose=2)
print(f'Test loss: {test_scores[0]}')
print(f'Test accuracy: {test_scores[1]}')
```

This example creates a model with 2 hidden layers and 1 output layer. The first 2 hidden layers have 64 nodes each and use the ReLU activation function. The output layer has a single node and uses the sigmoid activation function. The model is trained using the Adam optimizer and binary cross-entropy loss. The accuracy metric is used to evaluate the model.

To use this code, you will need to replace X_train, y_train, X_val, y_val, X_test, and y_test with your own training, validation, and test data.

---

### Using PyTorch library
To implement Artificial Neural Networks (ANN) using PyTorch, you can follow these general steps:

```python
# Import the necessary libraries: PyTorch, NumPy, and Pandas.
import torch
import numpy as np
import pandas as pd

# Load the dataset: You can use Pandas to load the dataset.
data = pd.read_csv('dataset.csv')

# Split the dataset into training and testing sets:
from sklearn.model_selection import train_test_split
X_train, X_test, y_train, y_test = train_test_split(data.iloc[:, :-1], data.iloc[:, -1], test_size=0.2, random_state=0)

# Convert the data into PyTorch tensors:
X_train = torch.from_numpy(np.array(X_train)).float()
y_train = torch.from_numpy(np.array(y_train)).float()

X_test = torch.from_numpy(np.array(X_test)).float()
y_test = torch.from_numpy(np.array(y_test)).float()

# Define the neural network architecture: You can define the neural network using the torch.nn module.
class ANN(torch.nn.Module):
    def __init__(self):
        super(ANN, self).__init__()
        self.fc1 = torch.nn.Linear(8, 16)
        self.fc2 = torch.nn.Linear(16, 8)
        self.fc3 = torch.nn.Linear(8, 1)
        
    def forward(self, x):
        x = torch.relu(self.fc1(x))
        x = torch.relu(self.fc2(x))
        x = torch.sigmoid(self.fc3(x))
        return x

model = ANN()

# In this example, we define an ANN with 3 fully connected layers, where the first two layers have a ReLU activation function and the last layer has a sigmoid activation function.

# Define the loss function and optimizer:
loss_fn = torch.nn.BCELoss()
optimizer = torch.optim.Adam(model.parameters(), lr=0.001)

# Train the model:
for epoch in range(100):
    y_pred = model(X_train)
    loss = loss_fn(y_pred, y_train.unsqueeze(1))
    optimizer.zero_grad()
    loss.backward()
    optimizer.step()

# Test the model:
y_pred_test = model(X_test)
y_pred_test = (y_pred_test > 0.5).float()

from sklearn.metrics import accuracy_score
accuracy = accuracy_score(y_test, y_pred_test)

# Save the model:
torch.save(model.state_dict(), 'model.pth')
```

This is a general template for implementing an ANN using PyTorch. You can customize it based on your specific requirements.

---

In conclusion, ANNs are a powerful machine learning model that can be used to model non-linear relationships in data. The structure of an ANN consists of an input layer, one or more hidden layers, and an output layer. Python has several libraries that can be used to implement ANNs, including TensorFlow, Keras, and PyTorch.

Comments welcome!