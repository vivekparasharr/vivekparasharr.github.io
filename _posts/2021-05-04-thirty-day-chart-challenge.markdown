---
layout: post
title: "30 Day Daily Chart Challenge April 2021 - WIP"
categories: chart challenge, visualization, daily
---
During the month of April 2021, I participated in the [#30DayMapChallenge](https://github.com/Z3tt/30DayChartChallenge_Collection2021), a daily social data project hosted by [Cédric Scherer](https://github.com/z3tt), [Maya Gans](https://github.com/MayaGans) and [Dominic Royé](https://github.com/dominicroye). In this blog post I wanted to briefly talk about the project and share my experience, learnings in terms of data and tools used, and challenges faced. However, before I delve into that, here is a collage of [my submissions](/images/Challenges-and-Competitions/2021-04-Charts-Combined2.jpg). 

![charts-combined](/images/competitions/2021-04-Charts-Combined2.jpg){:class="img-responsive"}

### The ask
The project was about plotting a chart a day using any tool and any relevant dataset. Each day had a different theme and there were five main themes and then sub-themes within them as shown below. For example for day 1 part-to-whole comparison, one could plot the number of Indian Netflix viewers out of the total number of Netflix viewers across the world. For day 15 multivariate relationships, one could plot the relationship between technology indicators and stock market performance. 

![charts-guide](/images/competitions/2021-04-Charts-Combined3.png){:class="img-responsive"}

### My experience was 

### Tools used
I mainly used Python for plotting. There were several visualization libraries that I used such as [Plotly](https://plotly.com/python/), [Altair](https://altair-viz.github.io/), [Seaborn](https://seaborn.pydata.org/), [Matplotlib](https://matplotlib.org/), and [pandas.plot](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.plot.html). I wanted to use [Bokeh](https://docs.bokeh.org/en/latest/docs/gallery.html) and [plotnine](https://plotnine.readthedocs.io/en/stable/) for later some submissions but did not have time alongside my job so ended up reusing some of the code from initial submissions. 

Additionally, one of the most useful library that I worked with was [dataprep](https://pypi.org/project/dataprep/). This is a fast and easy exploratory data analysis tool that allows one to understand a Pandas/Dask DataFrame with a few lines of code in seconds. I was able to quickly slice and dice data in a visual manner using the create_report function, thus enabling me to quickly decide if a particular dataset was relevant for the topic of the day. Following are some code snippets of how one can do that. 

```python
from dataprep.datasets import load_dataset
from dataprep.eda import create_report
df = load_dataset("titanic")
create_report(df).show_browser()
```

### Challenges faced
The biggest challenge was certainly in finding the right data. There were several websites that I used for this  were [data.world](https://data.world/), [kaggle](https://www.kaggle.com/datasets), [TidyTuesday](https://github.com/rfordatascience/tidytuesday/tree/master/data/2021), [MakeoverMonday](https://www.makeovermonday.co.uk/data/), 
[Eurostats](https://ec.europa.eu/eurostat), [UN Stats](https://unstats.un.org/home/), [WHO](https://www.who.int/data/collections), and [OECD Stats](https://stats.oecd.org/). 

Some code
```python
xx
```

For complete version of the code snapshots shown in this blog visit my [GitHub](https://github.com/vivekparasharr/Challenges-and-Competitions/tree/main/30DayChartChallenge). 

Comments welcome!

{% include disqus_comments.html %}
