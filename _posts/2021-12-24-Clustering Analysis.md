---
title: "Clustering Analysis of Rideshare Trips"
date: 2021-12-24
published: true
excerpt: "Spatial Clustering with DBSCAN"
toc: false

---

We used the DBSCAN algorithm to get the highest density clusters of rideshare trips based on the pick up and drop off points, the distance traveled, and the pick-up hour. Because of the data size, and because my laptop is giving up on me, we only got a random sample of 15% of the trips, which has 419,890 transactions. The eps is set at .2 and the min_samples is set at 50. There are 74 clusters, but we only extracted and visualized the top five. For the aqua cluster, the pick-up hour is around 4 pm and the average distance is 1.9 miles. For the fuschia cluster, the pick-up hour is around 3 pm and the average trip distance is 2.39 miles, while the trip distance in the yellow cluster averaged at 1.36 miles with the pick-up hour at 8:30. For the lime cluster, the average distance was 18 miles and the pick-up hour is 3 pm. These clusters are in or near the downtown so the trip distances tend to be shorter as expected.  

![dbscan-plot]({{ site.url }}{{ site.baseurl }}/assets/images/dbscan.png)

I also tried using different parameters, but.

