---
title: "Exploratory Analysis of Ridesharing in Chicago"
date: 2021-12-24
published: true
tags: [dataviz, matplotlib]
excerpt: "This is an example blog post that embeds a matplotlib image."
toc: true
toc_sticky: true
read_time: false
hv-loader:
 hv-chart-1: "charts/heatmap1.html"
---


## Data Cleaning

We read in our [trips] dataset for October 2021, which had over 5 million rows. After removing the NAs, we are left with 2.8 million rows. We then converted the data type of some fields and added new ones for data analysis. 

[trips]: https://data.cityofchicago.org/Transportation/Transportation-Network-Providers-Trips/m6dm-c72p

## When do people travel?

We examined the total number trips for each day in October. From the plot below, we see a cyclical pattern. The demand is highest during weekends, drops during the first half of the week, and slowly picks up. At its peak and minimum, the total count remained roughly the same, except during Halloween, where more people used ride share. 
![lineplot](https://github.com/wesleneuy/MUSA-550-Final-Project/blob/main/charts/lineplottrips.png)
uihu

![line-plot]({{ site.url }}{{ site.baseurl }}/assets/images/lineplottrips.png)

The heatmap below shows the trips counts for the month by the hour of the day. The demand is highest late at night or early in the morning. 
<div id="hv-chart-1"></div>

## How far do people travel?

