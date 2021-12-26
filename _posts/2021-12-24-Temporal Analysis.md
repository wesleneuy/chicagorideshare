---
title: "Temporal Analysis of Ridesharing"
date: 2021-12-24
published: true
excerpt: "When do people use rideshare services?"
hv-loader:
 hv-chart-1: ["charts/heatmap1.html", "400"]
 toc: true
toc_sticky: true
read_time: false
---


## Data Cleaning
We read in our [trips] dataset for October 2021, which had over 5 million rows. After removing the NAs, we were left with 2.8 million transactions. We then converted the data type of some fields and added new ones for data analysis. 

```python
#loading the TNC data set
df = pd.read_csv("tnc_trips.csv")

#removing the space bet column names
df.columns = df.columns.str.replace(' ', '')

#dropping NAs
df = df.dropna()

#changing some data type to ojbects; use replace to drop the decimals
df.PickupCensusTract = df.PickupCensusTract.astype(str).replace('\.0', '', regex=True)
df.DropoffCensusTract = df.DropoffCensusTract.astype(str).replace('\.0', '', regex=True)

#converting to datetime
df.TripStartTimestamp = df.TripStartTimestamp.astype('datetime64[ns]')
df.TripEndTimestamp = df.TripEndTimestamp.astype('datetime64[ns]')

#extracting m/d/h/m for trip start
df['Start_Weekday'] = df['TripStartTimestamp'].dt.day_name()
df['Start_Day'] = df['TripStartTimestamp'].dt.day
df['Start_Hour'] = df['TripStartTimestamp'].dt.hour
df['Start_Minute'] = df['TripStartTimestamp'].dt.minute
```

[trips]: https://data.cityofchicago.org/Transportation/Transportation-Network-Providers-Trips/m6dm-c72p

## When do people travel?
We examined the total number trips for each day in October. From the plot below, we see a cyclical pattern. The demand is highest during weekends, drops during the first half of the week, and slowly picks up towards the middle and end of the week. At its peak and trough, the total count remained roughly the same, except during Halloween, where more people used ride share. 

![line-plot]({{ site.url }}{{ site.baseurl }}/assets/images/lineplottrips.png)

The heatmap below shows the trips counts for the month by the hour of the day. The demand is highest late at night or early in the morning. 
<div id="hv-chart-1"></div>

## How far and how long do people travel?
We visualized the distribution of the distance and duration of each trip. The distributions for both are skewed to the right, which means that we have outliers in the dataset. Trips for the month averaged at 4.7 miles and lasted 939 seconds (around 15 minutes).

![dist-plot]({{ site.url }}{{ site.baseurl }}/assets/images/displotmilesseconds.png)

## Which day of the week has the worst traffic overall?
Ridehailing services have been [blamed for making traffic congestion worse]. We calculated the average trip speed (in miles per hour) as a proxy variable for congestion. During peak hours (ie, 7 to 9 am), we would expect the trip speed to be slower. However, trip speeds are slowest from 4 to 6 am and not during rush hours. 

![speed-plot]({{ site.url }}{{ site.baseurl }}/assets/images/speed.png)

[blamed for making traffic congestion worse]: https://www.cmap.illinois.gov/documents/10180/844024/03.16_18_Whats+making+traffic+worse+in+Chicago+Signs+point+to+Uber+Lyft_CRAINS.pdf/143a4c91-bbae-04b3-2359-d03118159b7e

## How much do people pay for their trips?
We also looked at the fare by the hour of the day. Surprisingly, fares are also highest from 4 to 6 am. We suspect that this is because of the surge in demand at O'Hare International Airport. We will explore this further in the next section.
![fare1-plot]({{ site.url }}{{ site.baseurl }}/assets/images/fare1.png)

Rideshare users spent an average of $17 per trip in October. Longer distances does not necessarily mean higher fares as some passengers may opt for larger vehicles, among other factors. 
![fare2-plot]({{ site.url }}{{ site.baseurl }}/assets/images/fare2.png)
