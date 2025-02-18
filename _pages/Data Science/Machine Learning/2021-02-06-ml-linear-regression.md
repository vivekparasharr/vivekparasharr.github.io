---
title: "Implementing Linear Regression in Python and R"
date: "2021-02-06"
tags:
    - machine-learning
    - regression
    - linear-regression
    - linear
thumbnail: "/assets/img/placeholder.jpg"
---
Regression is a supervised learning technique to predict the value of a continuous target or dependent variable using a combination of predictor or independent variables. Linear regression is a type of regression where the primary consideration is that the independent and dependent variables have a linear relationship. Linear regression is of two broad types - simple linear regression and multiple linear regression. In simple linear regression there is only one independent variable. Whereas, multiple linear regression refers to a statistical technique that uses two or more independent variables to predict the outcome of a dependent variable. Linear regression also has some modifications such as lasso, ridge or elastic-net regression. However, in this article we will cover multiple linear regression. 

## Intuition behind linear regression
Before we begin, let us take a look at the equation of multiple linear regression. Y is the target variable that we are trying to predict. x1, x2, .. , xn are the n predictor variables. b0, b1, .. , bn are the n constants that the linear regression (OLS - ordinary least square) model will help us figure out. Example, we can use linear regression to predict a real value, like profit. 
```
Y = b0 + b1*x1 + b2*x2 + .. + bn*xn
profit = b0 + b1*r_n_d_spend + b2*administration + b3*marketing_spend + b4*state
```

The ordinary least squares method gets the best fitting line by identifying the line that minimizes square of distance between actual and predicted values. 
```
sum ( y_actual - y_hat ) ^ 2 -> minimize
```

## Assumptions of linear regression
Before we apply the linear regression model, we also need to check if the following assumptions hold true. 
- Linearity: The relationship between X and the mean of Y is linear
- Homoscedasticity: The variance of residual is the same for any value of X
- Independence: Observations are independent of each other
- Normality: For any fixed value of X, Y is normally distributed

## Implementing the model in python and R
Implementing the model consists of the following key steps. 
- Data pre-processing: This is similar for most ML models, so we tackle this in a separate article and not here
- Training the model
- Using the model for prediction

### Data pre-processing
At this stage we do several pre-processing activities including splitting the data into training set and test set. We usually can follow the 80:20 principle, meaning that we use 80% of our data to train the model and remaining 20% of the data to test the model, and catch under or overfitting. 

### Training the model
We use the ordinary least squares method to obtain an equation that predicts the dependent variable using independent variables from the training set. 

#### Using python
```python
from sklearn.linear_model import LinearRegression
regressor = LinearRegression()
regressor.fit(X_train, y_train)
```

#### Using R
```R
regressor = lm(formula = Profit ~ ., data = training_set)
```

### Using the model
Now, we use the obtained equation to predict the dependent variable using the test set independent variables. 

#### Using python
```python
y_pred = regressor.predict(X_test)
```

#### Using R
```R
y_pred = predict(regressor, newdata = test_set)
```

### Visualizing results
Visualising actual (x-axis) vs predicted (y-axis) test set values

#### Using python
```python
plt.scatter(y_test, y_pred) 
```

#### Using R
```R
ggplot() + geom_point(aes(x = test_set$Profit, y = y_pred))
```

For full implementation, check out my [github repository - python](https://github.com/vivekparasharr/Learning-Data-Science/blob/main/ML-in-Python/02_regression/05_multiple_linear_regression.py) and [github repository - R](https://github.com/vivekparasharr/Learning-Data-Science/blob/main/ML-in-R/02_regression/multiple_linear_regression.R). 

Comments welcome!