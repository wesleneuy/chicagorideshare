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

We examined the total number trips for each day in October. From the plot below, we see a cyclical pattern. The demand is highest during weekends, drops during the first half of the week, and slowly picks up towards the middle and end of the week. At its peak and trough, the total count remained roughly the same, except during Halloween, where more people used ride share. 


![line-plot]({{ site.url }}{{ site.baseurl }}/assets/images/lineplottrips.png)

The heatmap below shows the trips counts for the month by the hour of the day. The demand is highest late at night or early in the morning. 
<div id="hv-chart-1"></div>

## How far and how long do people travel?

## Which day of the week has the worst traffic overall?
Ridehailing services have been [blamed for making traffic congestion worse]. To serve as an indicator for congestion, we calculated the average trip speed (in miles per hour). From the plot below, trip speeds are slowest from 4 to 6 am, and not during rush hours (ie, 7 to 9 am) as one would expect. 

![speed-plot]({{ site.url }}{{ site.baseurl }}/assets/images/speed.png)

[blamed for making traffic congestion worse]: https://www.cmap.illinois.gov/documents/10180/844024/03.16_18_Whats+making+traffic+worse+in+Chicago+Signs+point+to+Uber+Lyft_CRAINS.pdf/143a4c91-bbae-04b3-2359-d03118159b7e

## How much do people pay for their trips?
We also looked at the trip fare by the hour of day. The plot below tells a similar story: fares are higher from 4 to 6 am. We suspect that this is because of the surge in demand at O'Hare International Airport. We will explore this further in the next sections.
![fare1-plot]({{ site.url }}{{ site.baseurl }}/assets/images/fare1.png)

![fare2-plot]({{ site.url }}{{ site.baseurl }}/assets/images/fare2.png)
