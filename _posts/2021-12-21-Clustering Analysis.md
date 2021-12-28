---
title: "Clustering Analysis of Rideshare Trips"
date: 2021-12-21
published: true
excerpt: "Spatial Clustering with K-Means and DBSCAN"
altair-loader:
  altair-chart-1: "charts/kcluster.json"
toc: true
toc_sticky: true

---
## K-Means Cluster

We clustered census tracts based on rideshare statistics. We took the average trip distances and start hours as well as the total count of trips for each census tract. Using the elbow method, we determined that the optimal number of clusters is 4.

![elbow-plot]({{ site.url }}{{ site.baseurl }}/assets/images/elbow.png)

The census tracts are colored by their cluster groups. Cluster 2 had the largest number of counts, with 1.5 million rideshare trips for the month. Cluster 3, which had less census tracts but include the downtown and O'Hare International Airport, had 1.2 million rideshare trips in October. Cluster 0, which are census tracts on the fringes of Chicago, had the longest average trip distances at 11 miles. On average, start trips range from 12 to 3 pm. 

<div id="altair-chart-1"></div>


## DBSCAN

We also used the DBSCAN algorithm to get the highest density clusters of rideshare trips based on the pick up and drop off points, the distance traveled, and the pick-up hour. Because of the data size, and because my laptop is giving up on me, we only got a random sample of 15% of the trips, which has 419,890 transactions. The eps is set at .2 and the min_samples is set at 50. There are 74 clusters, but we only extracted and visualized the top five. For the aqua cluster, the pick-up hour is around 4 pm and the average distance is 1.9 miles. For the fuschia cluster, the pick-up hour is around 3 pm and the average trip distance is 2.39 miles, while the trip distance in the yellow cluster averaged at 1.36 miles with the pick-up hour at 8:30 pm. These clusters are in or near the downtown so the trip distances tend to be shorter as expected. For the lime cluster, which are the neighborhoods in the northside of Chicago, the average distance was 18 miles and the pick-up hour is 3 pm. The trip distances are longer likely because rideshare passengers travel to Chicago's downtown. 

![dbscan-plot]({{ site.url }}{{ site.baseurl }}/assets/images/dbscan.png)

Note: I am unsure why less points are plotted in the image above compared to the NYC taxi rides example in Lecture 10B. I the tried using different parameters and also tried converting the lat and lng to meters but these didn't make any difference. 

