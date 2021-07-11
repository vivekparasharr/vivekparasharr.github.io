---
layout: post
title: "Statistical Distributions!"
categories: statistics, describe, data, mean, variance, standard deviation, normal, skewness, kurtosis
---
### Statistical Distributions!
##### The normal distribution is the most important probability distribution in statistics because it fits many natural phenomena.

In this article we will cover some distributions that I have found useful while analysing data. I have split them based on whether they are for a continuous or a discrete random variable. First I give a small theoretical introduction about the distribution, its probability density function, and then how to use python to represent it graphically.  

![combined](/images/distributions/2021-04-09.png){:class="img-responsive"}

Continuous Distributions:
- Uniform distribution
- Normal Distribution, also known as Gaussian distribution
- Standard Normal Distribution - case of normal distribution where loc or mean = 0 and scale or sd = 1 
- Gamma distribution - exponential, chi-squared, erlang distributions are special cases of the gamma distribution
- Erlang distribution - special form of Gamma distribution when a is an integer ?
- Exponential distribution - special form of Gamma distribution with a=1
- Lognormal - not covered
- Chi-Squared - not covered
- Weibull - not covered
- t Distribution - not covered
- F Distribution - not covered

Discrete Distributions:
- Poisson distribution is a limiting case of a binomial distribution under the following conditions: n tends to infinity, p tends to zero and np is finite
- Binomial Distribution
- Negative Binomial - not covered
- Bernoulli Distribution is a special case of the binomial distribution where a single trial is conducted n=1
- Geometric - not covered

Lets import some basic libraries that we will be using:
```python
import numpy as np
import pandas as pd
import scipy.stats as spss
import plotly.express as px
import seaborn as sns
```

### Continuous Distributions

#### Uniform distribution
As the name suggests, in uniform distribution the probability of all outcomes is same. The shape of this distribution is a rectange. Now, lets plot this using python. First we will generate an array of random variables using scipy. We will specifically use scipy.stats.uniform.rvs function with following three inputs:
- size specifies number of random variates
- loc corresponds to mean
- scale corresponds to standard deviation
```python
rv_array = spss.uniform.rvs(size=10000, loc = 10, scale=20) 
```

Now we can plot this using the plotly library or the seaborn library. Infact seaborn has a couple of different function, namely the distplot and the histplot, both of which can be used to visually view the unoform data. Lets see the examples one by one:

![uniform](/images/distributions/uniform.png){:class="img-responsive"}

We can directly plot the data from the array:
```python
px.histogram(rv_array) # plotted using plotly express
sns.histplot(rv_array, kde=True) # plotted using seaborn
```

![uniform-labels](/images/distributions/uniform-labels.png){:class="img-responsive"}

Or we can convert array into a dataframe and then plot the data frame:
```python
rv_df = pd.DataFrame(rv_array, columns=['value_of_random_variable'])
px.histogram(rv_df, x='value_of_random_variable', nbins=20) # plotted using plotly express
sns.histplot(data=rv_df, x='value_of_random_variable', kde=True) # plotted using seaborn
```

#### Normal Distribution, also known as Gaussian distribution: 
The normal distribution is the most important probability distribution in statistics because it fits many natural phenomena. 
Normal distribution is a limiting case of Poisson distribution with the parameter lambda tends to infinity. Additionally since poisson distribution is a for of binomial distribution, normal distribution is also a form of binomial distribution. 
This distribution has a bell-shaped density curve described by its mean and standard deviation. The mean represents the location and the sd represents the spread of the distribution. The curve represents that the data near the mean occurrs more frequently than the data far from the mean. 

Lets plot it using seaborn:

![normal](/images/distributions/normal.png){:class="img-responsive"}

```python
rv_array = spss.norm.rvs(size=10000,loc=10,scale=100)  # size specifies number of random variates, loc corresponds to mean, scale corresponds to standard deviation
sns.histplot(rv_array, kde=True)
```

We can add x and y labels, change the number of bins, color of bars, etc. With distplot we can supply additional arguments for adjusting width of bars, transparency, etc.

![normal-colored](/images/distributions/normal-colored.png){:class="img-responsive"}

```python
ax = sns.distplot(rv_array, bins=100, kde=True, color='cornflowerblue', hist_kws={"linewidth": 15,'alpha':1})
ax.set(xlabel='Normal Distribution', ylabel='Frequency')
```
#### Standard Normal Distribution
Is a special case of the normal distribution where mean = 0 and sd = 1 

Lets plot it using seaborn:

![standard-normal](/images/distributions/standard-normal.png){:class="img-responsive"}

```python
rv_array = spss.norm.rvs(size=10000,loc=0,scale=1) 
sns.histplot(rv_array, kde=True)
```

#### Gamma distribution is a two-parameter family of continuous probability distributions
Exponential, chi-squared, erlang distributions are special cases of the gamma distribution

Lets plot it using seaborn:

![gamma](/images/distributions/gamma.png){:class="img-responsive"}

```python
rv_array = spss.gamma.rvs(a=5, size=10000) # size specifies number of random variates, a is the shape parameter
sns.distplot(rv_array, kde=True)
```

#### Erlang distribution 
Special case of Gamma distribution when a is an integer. 

#### Exponential distribution 
Special case of Gamma distribution with a=1. 
Exponential distribution describes the time between events in a Poisson point process, i.e., a process in which events occur continuously and independently at a constant average rate. 

Lets plot it using seaborn:

![exponential](/images/distributions/exponential.png){:class="img-responsive"}

```python
rv_array = spss.expon.rvs(scale=1,loc=0,size=1000) # size specifies number of random variates, loc corresponds to mean, scale corresponds to standard deviation
sns.distplot(rv_array, kde=True)
```

### Discrete Distributions

#### Binomial Distribution
Distribution where only two outcomes are possible, such as success or failure, gain or loss, win or lose. Additionally, the probability of success and failure is same for all the trials. Further, the outcomes need not be equally likely, and each trial is independent of each other.

The probability of observing k events in an interval is given by the equation: f(k;n,p) = nCk * (p^k) * ((1-p)^(n-k))
Where, nCk = (n)! / ((k)! * (n-k)!) 
n=total number of trials
p=probability of success in each trial

Lets plot it using seaborn:

![binomial](/images/distributions/binomial.png){:class="img-responsive"}

```python
rv_array = spss.binom.rvs(n=10,p=0.8,size=10000) # n = number of trials, p = probability of success, size = number of times to repeat the trials
sns.distplot(rv_array, kde=True)
```

#### Poisson Distribution
Poisson random variable is typically used to model the number of times an event happened in a time interval. For example, the number of users registered for a web service in an interval can be thought of as a Poisson process. Poisson distribution is described in terms of the rate (μ) at which the events happen. The average number of events in an interval is designated λ (lambda). Lambda is the event rate, also called the rate parameter. 
The probability of observing k events in an interval is given by the equation: P(k events in interval) = e^(-lambda) * (lambda^k / k!)

Poisson distribution is a limiting case of a binomial distribution under the following conditions:
- The number of trials is indefinitely large or n tends to infinity
- The probability of success for each trial is same and indefinitely small or p tends to zero
- np = lambda, is finite.

Lets plot it using seaborn:

![poisson](/images/distributions/poisson.png){:class="img-responsive"}

```python
rv_array = spss.poisson.rvs(mu=3, size=10000) # size specifies number of random variates, loc corresponds to mean, scale corresponds to standard deviation
sns.distplot(rv_array, kde=True)
```

#### Bernoulli distribution 
This distribution has only two possible outcomes, 1 (success) and 0 (failure), and a single trial, for example, a coin toss. The random variable X which has a Bernoulli distribution can take value 1 with the probability of success, p, and the value 0 with the probability of failure, q or 1-p. The probabilities of success and failure need not be equally likely. 
Probability mass function of Bernoulli distribution: f(k;p) = (p^k) * ((1-p)^(1-k))

Bernoulli distribution is a special case of the binomial distribution where a single trial is conducted (n=1)

Lets plot it using seaborn:

![bernoulli](/images/distributions/bernoulli.png){:class="img-responsive"}

```python
rv_array = spss.bernoulli.rvs(size=10000,p=0.6) # p = probability of success, size = number of times to repeat the trial
sns.distplot(rv_array, kde=True)
```

Hope you found this summary of distributions useful. I refer to this from time to time to jog my memory on the various distributions. 

Comments welcome!

{% include disqus_comments.html %}
