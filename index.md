---
layout: default
altair-loader:
  philadelphiarest: "charts/Philadelphia_Rest.json"
  Distribution_of_Yelp_Ratings: "Distribution_of_Yelp_Ratings.json"
  NumberofReviews: "NumberofReviews.json"
  Ratings_by_Food_Vio: "Ratings_by_Food_Vio.json"
  Ratings_by_Retail_Vio: "Ratings_by_Retail_Vio.json"

  
hv-loader:
  hv-chart-top_10: ["charts/Top_10_Inspection_Plot.html", "700"]
  Average-Retail: ["charts/Average Retail Violations by Category.html", 700"]
  Average-Food: ["charts/Average_Food_Violations_by_Category.html", 700]
  NeighborListandPlot: ["charts/NeighborListandPlot.html", 700]
  Top_10_Inspections: ["charts/Top_10_Inspection_Plot.html", 700]
  Top_Categories: ["charts/Top_Cuisine_Categories.html", 700]
  Top_Inspections: ["charts/Top_Inspections.html", 700]

  
  
  
---

# Yelp Ratings and Food Safety Inspections

by Rashon Clark


## Introduction
This project explores the relationship between Yelp restaurant ratings and food safety inspections from the Philadelphia Department of Health. We will interrogate the notion that customer satisfaction is really correlated with good sanitation practices, and if customers have any awareness of such problems. Yelp was chosen because of the availability of data and its longevity in the ratings sector, as well as its role as one of the broadest and widely used restaurant rating systems. Not only is it widely used by eaters, many establishments actively work to ensure positive ratings on the site. Similarly, the Department of Health is authority to which every food establishment is subject and with consistent standards.

## Data
Data from Yelp was drawn through the Yelp API and the food inspections data was scraped from the Philadelphia Inquirer’s portal for food inspections, which was made in conjunction with the Philadelphia Department of Health. The original dataset of Philadelphia restaurants on Yelp included about 20,000 entries and the scrapped inspections dataset included over 300,000 individual inspections. Nevertheless, once the two datasets were pared down to active restaurants, and those that had inspections, as well as unmergeable entries, the final merged dataset had about 1,500 restaurants. In general, the majority of these restaurants were concentrated in center city, the Passyunk area, Fishtown, and adjoining districts.

<div id="philadelphiarest"></div>

As can be seen in the below chart of the top Neighborhoods by inspections, Fishtown has the largest amount by many multiples of the rest. This may be a quirk of the two datasets, with Fishtown names and addresses merging better than other addresses. Fishtown may also have a more long-lived base of restaurants. Because the Yelp API only returns active restaurants, inspections from shuttered restaurants are invariably dropped from the dataset. Consequently, neighborhoods with a high business turnover at certain locations may have diminished visibility in the dataset.

### Ranked Neighborhoods by Inspection

For the actual number of restaurants represented in the data, the distribution is much more broad, with a similar amount of establishments across most of the neighborhoods. The key outliers with large numbers were expected, dining districts such as Rittenhouse, Washington Square, Old City, and Chinatown.

### Ranked Neighborhoods by Number 

The breakdown in regard to the most numerous categories was very interesting, with the top five common restaurant types being Pizza, Chinese, American, Delis, and Bakeries. In general, the different categories of cuisines feature similar average number of violations, with the exception of ice creameries.

### Average Violations by Food by Category

### Average Violations by Retail by Category

As for the Yelp ratings, the majority of restaurants were rated 3 (out of 5) or above. This shows that reviewers are generally positive. Indeed, the number of five-star ratings is three times or more any rating 2.5 or below. The data and model might be influenced by the fact that poor performing restaurants might have been purged through natural selection. Because the data only includes active restaurants, lower performing restaurants and those closed because of violations may have been absent from the data, thus reducing the influence poor practices and violations.

### Distribution of Yelp Ratings

Although the ratings data is very top-heavy, the two plots below demonstrate that there is a slight correlation between additional food and retail violations and a lower rating. As we move to the right, and the higher ratings, the average number of violations dips lower, although very slightly, for both retail and food safety violations. 

### Bar plot 1
### Bar plot 2

This is borne out in a correlation matrix of the data, which showed that the number of reviews, and the average number of each violation all had a correlation of about 20%. These slight correlations were enough to influence and improve my predictive model, which I will discuss below.


### Correlation matrix


A model was created to predict the Yelp rating of restaurants, and test our question about the influence of violations on Yelp rating. Of course, a disclaimer must be made that these investigations will only show correlation, and not causation. However, it is assumed that the violation record is capturing the same differences between restaurants that diners are capturing through their subjective experiences. I used the number of ratings, the average number of violations, the price rating, and zip code and category data. The returned a score of .21, meaning that the model accounted for a little over 20% of the variation between the rating of the restaurants. The average violations were also the most importance features, which is consistent with the correlation matrix and the data visualizations. 

### Important Features

The aim of this project was to examine the relationship between violations and customer satisfaction, via the Yelp Rating. The conclusion of this project is that violations have a slight correlation with the general understanding of customer satisfaction. This makes sense, since most diners do not go to restaurants with violation data in mind, but it seems that violations can capture some of the elements which cause dissatisfaction among customers, particularly poor sanitation and retail practices. Nevertheless, these are not the only reasons diners enjoy or avoid food, and certain establishments may have brands that supersede any poor practices.

