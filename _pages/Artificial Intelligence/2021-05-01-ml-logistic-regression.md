---
title: "Implementing Logistic Regression in Python and R"
date: "2021-05-01"
tags:
    - machine-learning
    - classification
    - logistic-regression
    - logistic
thumbnail: /assets/img/images-for-pages/artificial-intelligence/logistic-regression.png
---
Logistic regression is a type of statistical analysis (also known as logit model). It is often used for predictive analytics and modeling, and extends to applications in machine learning. In this analytics approach, the dependent variable is finite or categorical: either A or B (binary regression) or a range of finite options A, B, C or D (multinomial regression). It is used to understand the relationship between the dependent variable and one or more independent variables by estimating probabilities using a logistic regression equation.

This type of analysis can help you predict the likelihood of an event happening or a choice being made. For example, you may want to know the likelihood of a visitor choosing an offer made on your website — or not (dependent variable). Your analysis can look at known characteristics of visitors, such as sites they came from, repeat visits to your site, behavior on your site (independent variables). Logistic regression models help you determine a probability of what type of visitors are likely to accept the offer — or not. As a result, you can make better decisions about promoting your offer or make decisions about the offer itself.

## Logistic regression formula
Here p is the probability of a positive outcome.
```
Logit(p)  = log(p / (1-p))
```

## Types of logistic models
Following are some types of predictive models that use logistic analysis.
- Generalized linear model
- Discrete choice
- Multinomial logit
- Mixed logit
- Probit
- Multinomial probit
- Ordered logit

## Assumptions of logistic regression
Before we apply the logistic regression model, we also need to check if the following assumptions hold true. 
- The Response Variable is Binary
- The Observations are Independent - The easiest way to check this assumption is to create a plot of residuals against time (i.e. the order of the observations) and observe whether or not there is a random pattern. If there is not a random pattern, then this assumption may be violated.
- There is No Multicollinearity Among Explanatory Variables - The most common way to detect multicollinearity is by using the variance inflation factor (VIF), which measures the correlation and strength of correlation between the predictor variables in a regression model. 
- There are No Extreme Outliers - The most common way to test for extreme outliers and influential observations in a dataset is to calculate Cook’s distance for each observation. If there are indeed outliers, you can choose to (1) remove them, (2) replace them with a value like the mean or median, or (3) simply keep them in the model but make a note about this when reporting the regression results.
- There is a Linear Relationship Between Explanatory Variables and the Logit of the Response Variable. The easiest way to see if this assumption is met is to use a Box-Tidwell test.

![Logistic regression](/assets/img/images-for-pages/artificial-intelligence/logistic-regression.png){:class="img-responsive"}

## Implementing the model in python and R
Implementing the model consists of the following key steps. 
- Data pre-processing: This is similar for most ML models, so we tackle this in a separate article and not here
- Training the model
- Using the model for prediction

### Data pre-processing
At this stage we do several pre-processing activities including splitting the data into training set and test set. We usually can follow the 80:20 principle, meaning that we use 80% of our data to train the model and remaining 20% of the data to test the model, and catch under or overfitting. 

### Training the model
We use the generalized linear model to obtain an equation that predicts the dependent variable using independent variables from the training set. 

#### Using python
```python
from sklearn.linear_model import LogisticRegression
classifier = LogisticRegression(random_state = 0)
classifier.fit(X_train, y_train)
```

#### Using R
```R
classifier = glm(formula = Purchased ~ ., family = binomial, data = training_set)
```

### Using the model
Now, we use the obtained equation to predict the dependent variable using the test set independent variables. 

#### Using python
```python
y_pred = classifier.predict(X_test)
```

#### Using R
```R
prob_pred = predict(classifier, type = 'response', newdata = test_set[-3])
y_pred = ifelse(prob_pred > 0.5, 1, 0)
```

### Visualizing results
Visualising the outcome of the model through a confusion matrix. 

#### Using python
```python
from sklearn.metrics import confusion_matrix, accuracy_score
cm = confusion_matrix(y_test, y_pred)
accuracy_score(y_test, y_pred)
```

#### Using R
```R
cm = table(test_set[, 3], y_pred > 0.5)
```

For full implementation, check out my [github repository - python](https://github.com/vivekparasharr/Learning-Data-Science/blob/main/ML-in-Python/03_classification/logistic_regression.py) and [github repository - R](https://github.com/vivekparasharr/Learning-Data-Science/blob/main/ML-in-R/03_classification/logistic_regression.R). 

Comments welcome!