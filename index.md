---
layout: default
toc: false
toc_sticky: false
altair-loader:
  philadelphiarest: "charts/Philadelphia_Rest.json"
  Distribution_of_Yelp_Ratings: "Distribution_of_Yelp_Ratings.json"
  NumberofReviews: "NumberofReviews.json"
  Ratings_by_Food_Vio: "Ratings_by_Food_Vio.json"
  Ratings_by_Retail_Vio: "Ratings_by_Retail_Vio.json"

  
hv-loader:
  hv-chart-top_10: ["charts/Top_10_Inspection_Plot.html", "800"]
  Average-Retail: ["charts/Average Retail Violations by Category.html", 800"]
  Average-Food: ["charts/Average_Food_Violations_by_Category.html"]
  NeighborListandPlot: ["charts/NeighborListandPlot.html"]
  Top_10_Inspections: ["charts/Top_10_Inspection_Plot.html"]
  Top_Categories: ["charts/Top_Cuisine_Categories.html"]
  Top_Inspections: ["charts/Top_Inspections.html"]

  
  
  
---

# Yelp Ratings and Food Safety Inspections

by Rashon Clark


## Introduction
This project explores the relationship between Yelp restaurant ratings and food safety inspections from the Philadelphia Department of Health. We will interrogate the notion that customer satisfaction is really correlated with good sanitation practices, and if customers have any awareness of such problems. Yelp was chosen because of the availability of data and its longevity in the ratings sector, as well as its role as one of the broadest and widely used restaurant rating systems. Not only is it widely used by eaters, many establishments actively work to ensure positive ratings on the site. Similarly, the Department of Health is authority to which every food establishment is subject and with consistent standards.

## Data
Data from Yelp was drawn through the Yelp API and the food inspections data was scraped from the Philadelphia Inquirer’s portal for food inspections, which was made in conjunction with the Philadelphia Department of Health. The original dataset of Philadelphia restaurants on Yelp included about 20,000 entries and the scrapped inspections dataset included over 300,000 individual inspections. Nevertheless, once the two datasets were pared down to active restaurants, and those that had inspections, as well as unmergeable entries, the final merged dataset had about 1,500 restaurants. In general, the majority of these restaurants were concentrated in center city, the Passyunk area, Fishtown, and adjoining districts.

<div id="philadelphiarest"></div>

As can be seen in the below chart of the Top 20 Neighborhoods by inspections, Fishtown has the largest amount by many multiples of the rest. This may be a quirk of the two datasets, with Fishtown names and addresses merging better than other addresses. Fishtown may also have a more long-lived base of restaurants. Because the Yelp API only returns active restaurants, inspections from shuttered restaurants are invariably dropped from the dataset. Consequently, neighborhoods with a high business turnover at certain locations may have diminished visibility in the dataset.



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

