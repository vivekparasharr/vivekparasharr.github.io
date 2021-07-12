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
I mainly used Python for plotting. There were several visualization libraries that I used such as [Plotly](https://plotly.com/python/), [Altair](https://altair-viz.github.io/), [Seaborn](https://seaborn.pydata.org/), [Matplotlib](https://matplotlib.org/), and [pandas.plot](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.plot.html). I wanted to use [Bokeh](https://docs.bokeh.org/en/latest/docs/gallery.html) and [plotnine](https://plotnine.readthedocs.io/en/stable/) for later some submissions but did not have time alongside my job so ended up reusing some of the code from initial submissions. Overall, I found that Plotly was best for customization while Seaborn and Altair let you create some neat charts very quickly. For the rest of this articles I will focus on Plotly.

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



For day 3, I found an interesting dataset on OWID about the number of working hours. In general the working hours in most countries have gone down over time with a few exceptions. Used Plotly to create a line chart that shows this. The y-axis shows Average working hours per worker over a full year. Used a for loop to add each line to the plot with a separate color. 
```python
for i in range(0, y_axis_levels):
    fig.add_trace(go.Scatter(x=x_data[i], y=y_data[i], mode='lines',
        name=y_axis_labels[i],
        line=dict(color=colors[i], width=line_size[i]),
        connectgaps=True,
    ))
```
![chart03](/images/charts/2021-04-03.png){:class="img-responsive"} 


For day 5, I found an interesting dataset on OWID about the energy use per person by country. In general the energy use has been increasing dramatically with some of the most developed countries with the highest energy used per capita. Tried to capture this across time using a slope chart plotted using Plotly. Used for loop to plot separate lines for each country and added separate lines to reflect time. 
```python
# lines by country
for x_val, y_val, cat_val in zip(year1val, year2val, cat1val):
    fig.add_trace(go.Scatter(x=[year1, year2], y=[x_val, y_val], mode='lines+markers+text', text=[cat_val, cat_val], textposition=['middle left', 'middle right'] ))
# vertical lines representing time
fig.add_shape(type="line", x0=year1, y0=vp_min, x1=year1, y1=vp_max,line=dict(color="Grey",width=2))
fig.add_shape(type="line", x0=year2, y0=vp_min, x1=year2, y1=vp_max,line=dict(color="Grey",width=2))
```
![chart05](/images/charts/2021-04-05.png){:class="img-responsive"} 



For complete version of the code snapshots shown in this blog visit my [GitHub](https://github.com/vivekparasharr/Challenges-and-Competitions/tree/main/30DayChartChallenge). 

Comments welcome!

{% include disqus_comments.html %}
