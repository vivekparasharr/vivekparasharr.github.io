---
title: "Statistical Hypothesis Testing"
date: "2020-09-05"
tags:
    - statistics
    - hypothesis
    - hypothesis-testing
    - t-test
thumbnail: "/assets/img/images-for-pages/coding-and-maths/hypothesis-testing-process.png"
---
Hypothesis testing is a statistical method used to determine whether a hypothesis about a population parameter is supported by the data. It is a powerful tool for making decisions based on data, and is widely used in many fields including medicine, social sciences, and business.

![Hypothesis testing process](/assets/img/images-for-pages/coding-and-maths/hypothesis-testing-process.png){:class="img-responsive"}

# The basic steps in hypothesis testing are as follows:

- Formulate the null and alternative hypotheses: The null hypothesis is the statement that the population parameter is equal to a specified value, while the alternative hypothesis is the statement that the population parameter is not equal to the specified value. For example, if you want to test whether the mean height of a population is 65 inches, the null hypothesis would be "the mean height is equal to 65 inches" and the alternative hypothesis would be "the mean height is not equal to 65 inches."
- Choose a level of significance: The level of significance is the probability of rejecting the null hypothesis when it is actually true. Commonly used levels of significance are 0.05 (5%) and 0.01 (1%).
- Collect data and calculate test statistic: Next, you need to collect a sample of data and calculate a test statistic, which is a measure of how far the sample data is from what is expected under the null hypothesis. The test statistic will depend on the type of test being used, such as t-test or chi-squared test.
- Determine the p-value: The p-value is the probability of obtaining a test statistic as extreme or more extreme than the observed test statistic, assuming the null hypothesis is true. If the p-value is less than the chosen level of significance, then the null hypothesis is rejected and the alternative hypothesis is supported.
- Interpret the results: Finally, the results of the hypothesis test need to be interpreted in the context of the problem being studied. If the null hypothesis is rejected, it may be concluded that there is evidence to support the alternative hypothesis. However, if the null hypothesis is not rejected, it cannot be concluded that the null hypothesis is true, only that there is not enough evidence to reject it.

Hypothesis testing is a powerful tool for making decisions based on data, but it is important to use it correctly and to interpret the results carefully. When conducting a hypothesis test, it is important to ensure that the assumptions of the test are met, and to choose the appropriate test based on the type of data being analyzed. By following the steps outlined above and taking care to interpret the results correctly, hypothesis testing can be a valuable tool for making evidence-based decisions.

![Hypothesis test selection](/assets/img/images-for-pages/coding-and-maths/hypothesis-testing-select-test){:class="img-responsive"}

# There are many different types of hypothesis tests, each suited to different types of data and research questions. Here are a few of the most common types:

- One-sample t-test: This test is used to compare the mean of a single sample to a known or hypothesized population mean.
- Independent samples t-test: This test is used to compare the means of two independent groups.
- Paired samples t-test: This test is used to compare the means of two dependent (paired) groups.
- One-way ANOVA: This test is used to compare the means of more than two independent groups.
- Two-way ANOVA: This test is used to compare the means of two or more independent groups while controlling for one or more other variables.
- Chi-squared test: This test is used to compare the frequencies of categorical data between two or more groups.
- Mann-Whitney U test: This non-parametric test is used to compare the medians of two independent groups when the data are not normally distributed.
- Kruskal-Wallis test: This non-parametric test is used to compare the medians of more than two independent groups when the data are not normally distributed.
- Wilcoxon signed-rank test: This non-parametric test is used to compare the medians of two dependent groups when the data are not normally distributed.
- Friedman test: This non-parametric test is used to compare the medians of more than two dependent groups when the data are not normally distributed.

These are just a few examples of the many types of hypothesis tests that are used in statistical analysis. Choosing the right test for a given research question depends on the type of data being analyzed and the specific hypotheses being tested.

Comments welcome!