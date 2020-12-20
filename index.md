---
layout: default
toc: false
toc_sticky: false
altair-loader:
  philadelphiarest: "charts/Philadelphia_Rest.json"
  altair-chart-1: "charts/measlesAltair.json"
hv-loader:
  hv-chart-1: ["charts/measlesHvplot.html", "500"] # second argument is the desired height
  hv-chart-top_10: ["charts/Top_10_Inspection_Plot.html", "800"]
folium-loader:
  folium-chart-1: ["charts/foliumChart.html", "400"] # second argument is the desired height
  folium-chart-2: ["charts/percent_no_internet.html", "400"] # second argument is the desired height
---

# Yelp Ratings and Food Safety Inspections


## Introduction
This project explores the relationship between Yelp restaurant ratings and food safety inspections from the Philadelphia Department of Health. We will interrogate the notion that customer satisfaction is really correlated with good sanitation practices, and if customers have any awareness of such problems. Yelp was chosen because of the availability of data and its longevity in the ratings sector, as well as its role as one of the broadest and widely used restaurant rating systems. Not only is it widely used by eaters, many establishments actively work to ensure positive ratings on the site. Similarly, the Department of Health is authority to which every food establishment is subject and with consistent standards.

## Data
Data from Yelp was drawn through the Yelp API and the food inspections data was scraped from the Philadelphia Inquirer’s portal for food inspections, which was made in conjunction with the Philadelphia Department of Health. The original dataset of Philadelphia restaurants on Yelp included about 20,000 entries and the scrapped inspections dataset included over 300,000 individual inspections. Nevertheless, once the two datasets were pared down to active restaurants, and those that had inspections, as well as unmergeable entries, the final merged dataset had about 1,500 restaurants. In general, the majority of these restaurants were concentrated in center city, the Passyunk area, Fishtown, and adjoining districts.

<div id="philadelphiarest"></div>

As can be seen in the below chart of the Top 20 Neighborhoods by Inspections, Fishtown has the largest amount by many multiples of the rest. This may be a quirk of the two datasets, with Fishtown names and addresses merging better than other addresses. Fishtown may also have a more long-lived base of restaurants. Because the Yelp API only returns active restaurants, inspections from shuttered restaurants are invariably dropped from the dataset. Consequently, neighborhoods with a high business turnover at locations may have diminished visibility in the dataset.

<div id="hv-chart-top_10"></div>

# Example: Embedding Altair & Hvplot Charts

This section will show examples of embedding interactive charts produced using [Altair](https://altair-viz.github.io) and [Hvplot](https://hvplot.pyviz.org/).

## Altair Example

Below is a chart of the incidence of measles since 1928 for the 50 US states.
<div id="altair-chart-1"></div>
<div id="altair-chart-1"></div>

This was produced using Altair and embedded in this static web page. Note that you can also display Python code on this page:

```python
import altair as alt
alt.renderers.enable('notebook')
```

## HvPlot Example

Lastly, the measles incidence produced using the HvPlot package:

<div id="hv-chart-1"></div>

## Notes

- See the [raw source code](https://raw.githubusercontent.com/MUSA-550-Fall-2020/github-pages-starter/master/_posts/2019-04-13-measles-charts.md) of this post for details on how these charts were embedded.
- See the [lecture 13A slides](https://github.com/MUSA-550-Fall-2020/week-13/blob/master/lecture-13A.ipynb) for the code that produced these plots.

**Important: When embedding charts, you will likely need to adjust the width/height of the charts before embedding them in the page so they fit nicely when embedded.**

# Example: Embedding Folium charts

This post will show examples of embedding interactive maps produced using [Folium](https://github.com/python-visualization/folium).

## OSMnx and Street Networks

The shortest route between the Art Museum and the Liberty Bell:

<div id="folium-chart-1"></div>

<br/>

## Percentage of Households without Internet

The percentage of households without internet by county:

<div id="folium-chart-2"></div>

See the [lecture 9B slides](https://musa-550-fall-2020.github.io/slides/lecture-9B.html) and the [lecture 10A slides](https://musa-550-fall-2020.github.io/slides/lecture-10A.html) for the code that produced these plots.
