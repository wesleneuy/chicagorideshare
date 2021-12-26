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
We joined the trips data to the [geojson of census tracts] to get the geometries. The map below shows the count of pickup points by census tracts. Trip origins are mostly clustered around the Loop, O'Hare International Airport in the northwest, and Midway International Airport in the southwest side of Chicago. 

[geojson of census tracts]: https://data.cityofchicago.org/Facilities-Geographic-Boundaries/Boundaries-Census-Tracts-2010/5jrd-6zik

<div id="altair-chart-1"></div>

We also merged the trips data to the [neighborhoods geojson] in Chicago. The plot shows the top 10 neighborhoods with the largest number of pickup points. 

[neighborhoods geojson]: https://data.cityofchicago.org/Facilities-Geographic-Boundaries/Boundaries-Neighborhoods/bbvz-uum9

![neigh-plot]({{ site.url }}{{ site.baseurl }}/assets/images/neighborhoods.png)

## Where do trips end?
Dropoffs are also concentrated in the same census tracts, as shown in the map below.

<div id="altair-chart-2"></div>

## How far do rideshare users travel?
We also looked at the distance distribution based on the origin of rideshare users. Those who are booking a ride near the Loop tend to travel shorter distances, while those with pickup points farther from the downtown have longer trip distances.

![milespickup-plot]({{ site.url }}{{ site.baseurl }}/assets/images/tripmilespickup.png)


