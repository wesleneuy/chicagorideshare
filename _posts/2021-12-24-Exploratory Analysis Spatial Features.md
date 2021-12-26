---
title: "Spatial Analysis of Ridesharing"
date: 2021-12-24
published: true
excerpt: "Origins and destinations of rideshare trips"
altair-loader:
  altair-chart-1: "charts/pickups.json"
  altair-chart-2: "charts/dropoff.json"
toc: true
toc_sticky: true
---


## Where do trips begin?
The map below shows the count of pickup points by census tracts. Trip origins are mostly clustered around the Loop, O'Hare International Airport in the northwest, and Midway International Airport in the southwest side of Chicago. 

<div id="altair-chart-1"></div>


## Where do trips end?
Dropoffs are also concentrated in the same census tracts, as shown in the map below.

<div id="altair-chart-2"></div>

## How far do rideshare users travel?
We also looked at the distance distribution based on the origin of rideshare users. Those who are booking a ride near the Loop tend to travel shorter distances, while those with pickup points farther from the downtown have longer trip distances.

![milespickup-plot]({{ site.url }}{{ site.baseurl }}/assets/images/tripmilespickup.png)


