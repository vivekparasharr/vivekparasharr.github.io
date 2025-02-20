---
title: "A Premier on Chi-squared test"
date: "2020-12-05"
tags:
    - statistics
    - hypothesis-testing
    - chi-square
    - python
thumbnail: "/assets/img/images-for-pages/coding-and-maths/chi-square.jpg"
---
The chi-square test is a statistical hypothesis test that is used to determine whether there is a significant association between two categorical variables. It is widely used in data analysis, particularly in fields such as social sciences, marketing, and biology, to examine relationships between categorical data. In this article, we will discuss the chi-square test, its applications, and how to perform it using Python.

![Chi-Square Distribution](/assets/img/images-for-pages/coding-and-maths/chi-square.jpg){:class="img-responsive"}

# Understanding the Chi-Square Test
The chi-square test is a non-parametric test that compares the observed frequencies of categorical data with the expected frequencies. The test is based on the chi-square statistic, which is calculated by summing the squared difference between the observed and expected frequencies, divided by the expected frequency, for each category.

The chi-square test is used to test the null hypothesis that there is no significant association between the two variables. If the calculated chi-square value is greater than the critical value, we can reject the null hypothesis and conclude that there is a significant association between the variables.

There are two types of chi-square tests: the chi-square goodness of fit test and the chi-square test of independence. The goodness of fit test is used to test whether the observed data follows a particular distribution, while the test of independence is used to test whether there is a significant association between two categorical variables.

# Applications of the Chi-Square Test
The chi-square test is widely used in research and data analysis, with a range of applications across various fields. Some common applications include:
- Market research: To determine if there is a significant association between demographic factors and consumer behavior, such as age, gender, and income level.
- Biology: To test whether different species of plants or animals are distributed randomly or in patterns in their environment.
- Social sciences: To test whether there is a significant relationship between socio-economic status and educational attainment.
- Quality control: To test whether a sample of products is defective, based on the number of products that pass or fail inspection.

# Performing the Chi-Square Test in Python
Python has several libraries that can be used to perform the chi-square test, including SciPy, Pandas, and StatsModels. Here is an example of how to perform the chi-square test of independence using the chi2_contingency function in the SciPy library:

```python
import scipy.stats as stats
import pandas as pd

# Load data into a Pandas DataFrame
data = pd.read_csv('my_data.csv')

# Create a contingency table
contingency_table = pd.crosstab(data['variable_1'], data['variable_2'])

# Perform the chi-square test of independence
chi2, p, dof, expected = stats.chi2_contingency(contingency_table)

# Print the results
print('Chi-square statistic:', chi2)
print('P-value:', p)
```

In this example, we load data from a CSV file into a Pandas DataFrame, create a contingency table using the crosstab function, and then use the chi2_contingency function to perform the chi-square test of independence. The function returns the chi-square statistic, the p-value, the degrees of freedom, and the expected frequencies.

# Conclusion
The chi-square test is a valuable statistical tool for examining the relationship between two categorical variables. By performing the test, we can determine whether there is a significant association between the variables and draw conclusions about the data. With the help of Python and its many data analysis libraries, we can easily perform the chi-square test and gain valuable insights from our data.

Comments welcome!