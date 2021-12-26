---
title: "Exploratory Analysis Spatial"
date: 2021-12-23
published: true
tags: [dataviz, altair, spatial]
excerpt: "Spatial analysis of rideshare trips"
altair-loader:
  altair-chart-1: "charts/pickups.json"
  altair-chart-2: "charts/dropoff.json"
toc: true
toc_sticky: true
---


## Where do trips begin?

Below is a chart of the incidence of measles since 1928 for the 50 US states.

<div id="altair-chart-1"></div>
<div id="altair-chart-2"></div>

This was produced using Altair and embedded in this static web page. Note that you can also display Python code on this page:

```python
import altair as alt
alt.renderers.enable('notebook')
```

## Where do trips end?

Lastly, the measles incidence produced using the HvPlot package:

<div id="hv-chart-1"></div>

## Notes

- See the [raw source code](https://raw.githubusercontent.com/MUSA-550-Fall-2021/github-pages-starter/main/_posts/2021-11-29-measles-charts.md) of this post for details on how these charts were embedded.
- See the [lecture 13A slides](https://github.com/MUSA-550-Fall-2021/week-13/blob/main/lecture-13A.ipynb) for the code that produced these plots.

**Important: When embedding charts, you will likely need to adjust the width/height of the charts before embedding them in the page so they fit nicely when embedded.**
