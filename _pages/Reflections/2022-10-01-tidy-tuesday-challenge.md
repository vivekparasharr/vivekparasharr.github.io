---
title: "TidyTuesday Weekly Visualization Challenge"
date: "2022-10-01"
tags:
    - data-viz
    - competition
    - tidytuesday
    - visualization
thumbnail: "/assets/img/images-for-pages/reflections/tidytuesday/tt_logo.png"
---
Since October 2020, I have been participating in TidyTuesday, a weekly social data project hosted by R for Data Science Online Learning Community. This enabled to me to quickly up-skill the visualization aspect of my data science journey. I also had the pleasure to engage with several likeminded people and curate and learn from their submissions and thought process. In the following post, I strive to share my experience and learnings. 

---

# Packages available for plotting
There are many Python packages available for plotting, each with its own strengths and weaknesses. Here are some of the most popular ones:
- Matplotlib: This is the most widely used library for creating static, interactive, and animated visualizations in Python. It is highly customizable and can create a wide variety of charts and graphs.
- Seaborn: Seaborn is built on top of Matplotlib and provides a high-level interface for creating statistical visualizations. It is particularly good for creating heatmaps, violin plots, and other complex visualizations.
- Plotly: This library provides interactive, web-based visualizations that can be embedded in websites or Jupyter notebooks. It supports a wide variety of chart types, including scatter plots, line charts, and 3D surface plots.
- Bokeh: Similar to Plotly, Bokeh provides interactive visualizations that can be embedded in web applications. It is particularly good for creating interactive scatter plots and geographical maps.
- plotnine: This library is based on the popular R package ggplot2 and provides a similar grammar for creating plots in Python. It is particularly good for creating aesthetically pleasing plots with minimal code.
- Altair: Altair is a declarative visualization library that allows you to create complex visualizations with minimal code. It uses a concise syntax that is based on the Vega-Lite visualization grammar.


![charts-combined](/assets/img/images-for-pages/reflections/tidytuesday/20210504.jpeg){:class="img-responsive"}
*Here is a snapshot of the visualizations I created on a dataset from Water Point Data Exchange.* 

---

# Considerations for plotting
While Python offers a wide variety of plotting libraries, there are still some challenges and considerations to keep in mind when plotting data. Here are a few:
- Data formatting: Before you can plot your data, you may need to format it properly. This can involve converting data types, cleaning up missing values, and transforming data into the right shape for a particular plot. This can be time-consuming and may require some knowledge of data manipulation in Python.
- Choosing the right plot: There are many types of plots to choose from, each with their own strengths and weaknesses. Choosing the right plot for your data can be challenging, especially if you are not familiar with the different types of plots available or if you are trying to convey complex relationships.
- Customizing the plot: Once you have chosen a plot, you may need to customize it to suit your needs. This can involve changing the colors, labels, and other visual properties of the plot. Customizing the plot can be time-consuming and may require some knowledge of the plotting library you are using.
- Performance: Depending on the size of your dataset and the complexity of your plot, generating a plot can be computationally intensive. This can lead to slow plot generation times, especially if you are working with large datasets or are trying to create interactive plots.
- Accessibility: When creating plots, it is important to consider accessibility for people with visual impairments. This can involve using high-contrast colors, providing alternative text descriptions, and ensuring that the plot is readable when printed in black and white.
- Reproducibility: If you are creating plots for research purposes, it is important to ensure that your plots are reproducible. This involves documenting the code and data used to create the plot, so that others can recreate the same plot in the future.

![charts-combined](/assets/img/images-for-pages/reflections/tidytuesday/20210420.jpeg){:class="img-responsive"}
*Here is a snapshot of the visualizations I created on a dataset that consists of tv shows and movies available on Netflix as of 2019.*

---

# Choosing the right plot to represent your data
Choosing the right kind of plot depends on several factors, including the type of data you are working with, the questions you want to answer, and the audience you are presenting to. The key is to choose a plot that effectively communicates your data and insights to your audience. It may be helpful to experiment with different types of plots and to seek feedback from others to ensure that your plot is clear and understandable. Here are some guidelines for choosing the right kind of plot for your data:
- Line charts: Line charts are useful for showing trends over time or for comparing trends between different groups. They work well for data that is continuous and evenly spaced, such as stock prices or weather data.
- Bar charts: Bar charts are useful for comparing values between different categories. They work well for data that is categorical or discrete, such as survey responses or sales data.
- Scatter plots: Scatter plots are useful for showing the relationship between two variables. They work well for data that is continuous and can show patterns or correlations in the data.
 Histograms: Histograms are useful for showing the distribution of a single variable. They work well for data that is continuous and can show the range, frequency, and shape of the data.
- Box plots: Box plots are useful for showing the distribution of a single variable across different groups. They work well for data that is continuous and can show the median, quartiles, and outliers in the data.
- Heatmaps: Heatmaps are useful for showing the relationship between two variables using color. They work well for data that is categorical or continuous and can show patterns or clusters in the data.
- Choropleth maps: Choropleth maps are useful for showing regional differences in data. They work well for data that is geographic in nature, such as population density or election results.

![charts-combined](/assets/img/images-for-pages/reflections/tidytuesday/20210601.jpeg){:class="img-responsive"}
*Here is a snapshot of the visualizations I created on a dataset detailing events across all 40 seasons of the US Survivor, including castaway information, vote history, immunity and reward challenge winners and jury votes.*

---

# Choosing the right package for building a particular plot
Here are some examples of plots that are specific to a particular Python package or easily built using a particular Python package:
- Violin plots: Violin plots are a type of plot that combine a box plot with a kernel density plot. They are commonly used for visualizing the distribution of a dataset. Violin plots can be easily built using the seaborn package, which provides tools for statistical visualization in Python.
- Sankey diagrams: Sankey diagrams are a type of flow diagram that show the flow of values between different categories. They can be easily built using the plotly package, which provides tools for creating interactive, web-based visualizations in Python.
- 3D surface plots: 3D surface plots are a type of plot that show the relationship between three variables. They can be easily built using the plotly or matplotlib package, which both provide tools for creating 3D visualizations in Python.
- Heatmaps: Heatmaps are a type of plot that show the relationship between two variables using color. They can be easily built using the seaborn package, which provides tools for statistical visualization in Python.
- Treemaps: Treemaps are a type of plot that show hierarchical data using nested rectangles. They can be easily built using the squarify package, which provides tools for creating treemaps in Python.

![charts-combined](/assets/img/images-for-pages/reflections/tidytuesday/20210518.jpeg){:class="img-responsive"}
*Here is a snapshot of the visualizations I created on a dataset detailing salaries and other information of 24,000+ survey participants.* 

---

# Benefits of interacting with other data visualization folks 
Interacting with other data visualization folks can offer several benefits, including:
- Learning new techniques: By interacting with other data visualization professionals, you can learn new techniques for creating effective visualizations. This can help you to improve your skills and create more compelling visualizations.
- Getting feedback: When you share your visualizations with other professionals, they can offer feedback on how to improve your work. This can help you to identify areas for improvement and create more effective visualizations.
- Discovering new tools: There are many different tools and libraries available for creating data visualizations in Python and other programming languages. By interacting with other professionals, you can discover new tools and libraries that can help you to create better visualizations.
- Finding inspiration: Sometimes, seeing how other professionals have approached data visualization can provide inspiration for your own work. By interacting with other professionals, you can see a variety of different approaches and ideas, which can help you to create more interesting and innovative visualizations.
- Building your network: Interacting with other data visualization professionals can help you to build your network and connect with others in your field. This can lead to new opportunities for collaboration and career advancement.

![charts-combined](/assets/img/images-for-pages/reflections/tidytuesday/20201201.jpeg){:class="img-responsive"}
*Here is a snapshot of the visualizations I created on a dataset about homeless shelters across Toronto, Canada.*


Overall, interacting with other data visualization professionals can help you to improve your skills, create more effective visualizations, and build your network. Whether through online communities, meetups, or conferences, there are many opportunities to connect with other professionals and benefit from their insights and expertise.

I would highly encourage others to participate in the #TidyTuesday weekly visualization challenge.

Comments welcome!