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



In the very first beginning,we loaded the Airbnb Listing data (from [InsideAirbnb][InsideAirbnb]) and cleaned the original dataset. To be more specific, we removed data that do not contain location information,then transformed datatype of certain fields(*e.g. price,host_response_rate*), and added new field `price_per_person` (*price_per_person=price/accommodates*) into our Airbnb dataset. Also, we loaded New York neighborhood data (from [NYC OpenData][NYC OpenData]), which served as a spatial reference for further analysis.


## When do people travel?

![lineplot](https://github.com/wesleneuy/MUSA-550-Final-Project/blob/main/charts/lineplottrips.png)
uihu



![line-plot]({{ site.url }}{{ site.baseurl }}/assets/images/lineplottrips.png

ed the Ai
<div id="hv-chart-1"></div>



