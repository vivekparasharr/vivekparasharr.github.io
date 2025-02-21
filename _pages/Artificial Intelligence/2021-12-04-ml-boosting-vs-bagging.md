---
title: "Boosting vs Bagging Model Improvement Techniques"
date: "2021-12-04"
tags:
    - machine-learning
    - boosting
    - bagging
thumbnail: "/assets/img/images-for-pages/artificial-intelligence/techniques-to-improve-models.png"
---
In machine learning, there are two popular techniques for improving the accuracy of models: boosting and bagging. Both techniques are used to reduce the variance of a model, which is the tendency to overfit to the training data. While they have similar goals, they differ in their approach and functionality. In this article, we'll explore the differences between boosting and bagging to help you decide which technique is right for your machine learning project.

![Techniques to improve models](/assets/img/images-for-pages/artificial-intelligence/techniques-to-improve-models.png){:class="img-responsive"}

## Bagging
Bagging, short for bootstrap aggregating, is a technique that involves training multiple models on different random subsets of the training data. The goal of bagging is to reduce the variance of a model by averaging the predictions of multiple models. Each model in the ensemble is trained independently and the final prediction is the average of all models. Bagging can be used with any algorithm, but it is most commonly used with decision trees. The most popular implementation of bagging is the random forest algorithm, which uses an ensemble of decision trees to make predictions.

## Boosting
Boosting is a technique that involves training multiple weak models on the same training data sequentially. The goal of boosting is to improve the accuracy of a model by adding new models that focus on the misclassified samples of the previous model. Each model in the ensemble is trained on the same dataset, but with different weights assigned to each sample. The weights are adjusted based on the misclassified samples of the previous model. The final prediction is a weighted average of all models in the ensemble. Boosting is commonly used with decision trees, but it can be used with any algorithm.

## Differences between Boosting and Bagging
While boosting and bagging have similar goals, they differ in their approach and functionality. The main differences between these two techniques are:
- Approach: Bagging involves training multiple models independently on different random subsets of the training data, while boosting trains multiple models sequentially on the same dataset with different weights assigned to each sample.
- Sample Weighting: Bagging assigns equal weight to each sample in the training data, while boosting assigns higher weight to misclassified samples.
- Model Selection: In bagging, the final prediction is the average of all models in the ensemble, while in boosting, the final prediction is a weighted average of all models in the ensemble.
- Performance: Bagging can reduce the variance of a model and improve its stability, but it may not improve its accuracy. Boosting can improve the accuracy of a model, but it may increase its variance and overfitting.

## Boosting vs Bagging Cimparison Implementation

```python
import numpy as np
import matplotlib.pyplot as plt
from sklearn.datasets import make_classification
from sklearn.model_selection import train_test_split
from sklearn.ensemble import BaggingClassifier, AdaBoostClassifier, GradientBoostingClassifier
from sklearn.tree import DecisionTreeClassifier
from sklearn.metrics import accuracy_score

# 1️⃣ Generate synthetic dataset
X, y = make_classification(n_samples=1000, n_features=20, random_state=42)
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.3, random_state=42)

# 2️⃣ Train Bagging Classifier (Bootstrap Aggregating)
bagging = BaggingClassifier(
    base_estimator=DecisionTreeClassifier(),  # Weak learner
    n_estimators=50,  # Number of trees
    random_state=42
)
bagging.fit(X_train, y_train)

# 3️⃣ Train Boosting Classifiers (AdaBoost & Gradient Boosting)
adaboost = AdaBoostClassifier(
    base_estimator=DecisionTreeClassifier(max_depth=1),  # Weak learner
    n_estimators=50,
    learning_rate=0.1,
    random_state=42
)
adaboost.fit(X_train, y_train)

gradient_boosting = GradientBoostingClassifier(
    n_estimators=50,
    learning_rate=0.1,
    max_depth=3,
    random_state=42
)
gradient_boosting.fit(X_train, y_train)

# 4️⃣ Evaluate performance
models = {"Bagging": bagging, "AdaBoost": adaboost, "Gradient Boosting": gradient_boosting}

for name, model in models.items():
    y_pred = model.predict(X_test)
    accuracy = accuracy_score(y_test, y_pred)
    print(f"{name} Accuracy: {accuracy:.4f}")

# 5️⃣ Visualize Feature Importance (Boosting Models)
plt.figure(figsize=(10, 5))
plt.bar(range(X.shape[1]), gradient_boosting.feature_importances_, color='blue', alpha=0.7)
plt.xlabel("Feature Index")
plt.ylabel("Feature Importance (Gradient Boosting)")
plt.title("Feature Importance - Gradient Boosting")
plt.show()
```

## Conclusion
In conclusion, boosting and bagging are two popular techniques for improving the accuracy of machine learning models. While they have similar goals, they differ in their approach and functionality. Bagging involves training multiple models independently on different subsets of the training data, while boosting trains multiple models sequentially on the same dataset with different weights assigned to each sample. Which technique is right for your machine learning project depends on your specific needs and goals. Bagging can improve model stability, while boosting can improve model accuracy.

Comments welcome!