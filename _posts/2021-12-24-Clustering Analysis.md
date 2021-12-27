---
title: "Clustering Analysis of Rideshare Trips"
date: 2021-12-24
published: true
excerpt: "Clustering rideshare trips"
toc: true
toc_sticky: true
---

We used DBSCAN to get the highest density clusters of rideshare trips based on the pick up and drop off points, the distance traveled, and the pick-up hour. Because of the data size, we only got a random sample of 15% of the trips, which has roughly 400,000 transactions. The eps is set as 250 meters. min_samples is set as 50.

After the clustering, the data are divided into 23 clusters, but we only extracted and visualized the top five clusters. Combined with the maps and the mean pick-up hour as well as the mean trip distance, we can infer the reasons for travel.

Based on the pick-up and drop-off location of the trips points in the top five clusters, we visualize patterns in the taxi trips. The color scheme is For example, for the yellow clusters which is the fifth biggest clusters in the table. For these trips, the pick-up hour is about 2:00 am and trip distance is relatively long. These trips started from the Midtown West to Upper East Side. We can infer that the reasons for the trips might be to go home after a wonderful Friday night.

Also, the number of each cluster in each taxi zones are computed and mapped. By the maps, we could easily know the distribution of certain type of trips.

This post will show examples of embedding interactive maps produced using [Folium](https://github.com/python-visualization/folium).

