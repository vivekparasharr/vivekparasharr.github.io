---
layout: post
title:  "30 Day Daily Map Challenge November 2020 - WIP"
date:   2020-12-05 16:09:00 -0300
categories: map challenge, gis data, daily
---
The #30DayMapChallenge was a daily social mapping project held in November 2020 that I participated in. I had a good understanding of Python before participating but very less knowledge of working with GIS data. So I had plotted some data on maps using Microsoft Excel, the data for which was usually in tabular format in an Excel or CSV. However, I had never heard of Shape files, DEM – Digital Elevation Models, DSM – Digital Surface Models, or DTM – Digital Terrain Models, etc. 

Understanding these formats, what they contain and how they can be processed was the first challenge I encountered. Python has a library called GeoPandas that makes it a breeze to deal with these file formats, however the challenge is to install it. GeoPandas usually has conflicts while installing and the best way that I found to install it was to first install Anaconda Python. Post that we create a new environment and install GeoPandas in that. 

![maps-combined](/images/Challenges-and-Competitions/2020-11-Maps-Combined2.jpg){:class="img-responsive"}

[HD Version](/images/Challenges-and-Competitions/2020-11-Maps-Combined.png)

'''python
conda create –n geopandas_env  Use below command to create a new environment
conda activate geopandas_env  Activate this environment
conda config — env — add channels conda-forge  # Add conda-forge channel to your environment
conda config — env — set channel_priority strict  # Make conda-forge your first priority to install any package so that dependent package won’t conflict
conda install python=3 geopandas  # Install GeoPandas using conda
'''

Now we have GeoPandas installed, lets move on to the interesting part. 

Comments welcome!

{% include disqus.html %}
