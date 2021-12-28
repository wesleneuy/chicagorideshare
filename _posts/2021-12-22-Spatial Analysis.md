---
title: "Spatial Analysis of Ridesharing"
date: 2021-12-22
published: true
excerpt: "Origins and destinations of rideshare trips"
altair-loader:
  altair-chart-1: "charts/pickups.json"
  altair-chart-2: "charts/dropoff.json"
hv-loader:
 hv-chart-1: ["charts/panel.html", "600"]  
toc: true
toc_sticky: true
---


## Where do trips begin?
We joined the trips data to the [census tracts boundaries] downloaded from Chicago's data portal to get the geometries. The map below shows the count of pickup points by census tracts. Trip origins are mostly clustered around the Loop, O'Hare International Airport in the northwest, and Midway International Airport in the southwest side of Chicago. 

[census tracts boundaries]: https://data.cityofchicago.org/Facilities-Geographic-Boundaries/Boundaries-Census-Tracts-2010/5jrd-6zik

<div id="altair-chart-1"></div>

We also merged the trips data to the [neighborhoods boundaries] in Chicago. The plot shows the top 10 neighborhoods with the largest number of pickup points. Aside from O'Hare, all of the top neighborhoods are in Chicago's downtown. 

[neighborhoods boundaries]: https://data.cityofchicago.org/Facilities-Geographic-Boundaries/Boundaries-Neighborhoods/bbvz-uum9

![neigh-plot]({{ site.url }}{{ site.baseurl }}/assets/images/neighborhoods.png)

## Where do trips end?
Dropoffs are also concentrated in the same census tracts, as shown in the map below.

<div id="altair-chart-2"></div>

## How far do rideshare users travel?
We also looked at the distance distribution based on the origin of rideshare users. Those who are booking a ride near the Loop tend to travel shorter distances, while those with pickup points farther from the downtown have longer trip distances.

![milespickup-plot]({{ site.url }}{{ site.baseurl }}/assets/images/tripmilespickup.png)

## How do rideshare trips vary by income?

We used CenPy to get income data and merged it with the census tracts and trips dataset. The API query only returned 664 tracts whereas the city's census tract boundaries has 801 tracts. The map below shows that more affluent households are concentrated in the downtown and northside of Chicago. 

![income-plot]({{ site.url }}{{ site.baseurl }}/assets/images/income.png)

Next, we looked at the relationship between income and distance, start hours, and trip counts. Lower income households seem to take longer trips and have earlier start hours.

<div id="hv-chart-1"></div>



