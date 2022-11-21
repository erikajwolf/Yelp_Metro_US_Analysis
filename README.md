# Yelp Metro US Analysis

## Objective
The objective of this project is to understand the different variables that impact the price for a given restaurant. To capture the differing demographic tendencies we looked at Washington State for the west coast, Illinois for the midwest and New York for the east coast. The project was aimed to understand how different demographics impacted the pricing for restaurants in their respective metropolitan areas.

In this analysis, we will aim to look at the combined analysis which will look at the west coast(WC), midwest (MW) and east coast(EC) in a single analysis as well as look at each geographic location on their own.

### Data Sources
This analysis takes in three data sources listed below:
* Yelp Business API: This data will be pulled directly from the Yelp business API which will help in creating the variable columns for the machine learning model. The variables being evaluated from this API are listed below
    * categories
    * rating
    * price
    * review count
    * city
    * state

* US Census Data: This data is pulled
to understand the demographics of each of the given geographic locations being analyzed. This table holds age demographic and income demographic data for the three state evaluated.

* US Zip Code Database: This data which is pulled form the United States Zip Codes site is used to evaluate which locations are considered metropolitan areas

* Metropolitan Areas: This paper provided guideance as to what determined if a geographic location was considered a metropolitan area. One of the main factors for determining the metropolitan area was the population density, in general a metropolitan area was considered to have >50,000 people in a given city. So this criteria was used to find the cities to evaluate.

Note: Due to the amount of data that would be pulled with the state of California, Washington state was used to analyze the WC.


### Analysis Criteria
Due to the limitation of our machines, we had to have a difinitive criteria as to what geographic locations we would analyze the Yelp restaurant data on. To begin the work we took the zip code database and included only those zip codes that had greater that 50,000 people in that given area looking across all of the 48 continuous states. However, in doing so, there was too much data to evaluate. To reduce the load, we were able to reduce the state down to Washinton, Illinois and New York in hopes to gather a board view of what trends were present in these given geographic area. 

## Combined Analysis
The combined analysis aimed to understand the themes present for the entire dataset that include WC, EC and MW.

This initial eploratory visual let us know that the number of restaurants were heavily weighted on the EC/New York, which let us know that a simple logistic regression would not paint the correct picture for us in understanding impacts the pricing rank of a restaurant on Yelp.

[State V. Reviews Count](/Resources/StateVReviewCounts.PNG)

In addition to the distribution of the restaurants being skewed to the EC, the income level for these three demographics show to be higher in the MW and the EC.

## Population Analysis
### Ages 25 & Under
When taking into account the income distribution of all people who are 25 & Under in all three locations, we can see that the median income is between \$5,000 - \$10,000/year range with Illinois having the higher range and Washington being closer to the $5,000 range. Comparing the distribution of this age group of all three geographic locations, it can also be seen that they are porportionately similar to each other. This can tell us that the weight of this this age groups income level will now skew the data any differently by geographic location.

[Washington Age Distribution](/Resources/Washington%20Combo.png)

[Illinois Age Distribution](/Resources/Illinois%20Combo.png)

[New York Age Distribution](/Resources/New%20York%20Combo.png)

[25 & Under: Income Distribution](/Resources/25AndUnder.PNG)

### Ages 26 thru 44
Similar to what we have seen in the 25 and under group the income level for those in the MW and EC are higher, with the disparity becoming more striking for this age group. The median income level seem to be relatively close for New York and Illinois being \$116,000 and \$75,00 respectively. In comparison the annual median income for Washington sits at about \$40,000 annually. 

As seen in the above visual for each states age distribution, we can conclude that they have similar distribution of each age group and therefore the age distribution will not skew our outcome.

[26 thru 44: Income Distribution](/Resources/26-44.PNG)

### Ages 45 thru 64
As we have seen in the 26 thru 44 age group, we can see that the median income levels for those in the MW and EC are higher with the WC not showing any growth in income levels. Same as above the age distribution is similar across all three geographic areas. 

[45 thru 64: Income Distribution](/Resources/45-64.PNG)

### Population Assumptions
Based on the separte data points we have for all three geographic locations, we made some preliminary assumptions that the distribution of $(one dollar sign) restaurants would be higher for our WC restaurant analysis and the key variables might be different than that of the EC and WC restaurants in this analysis. 

Additionally, the age demographic that impact the number of restuarants with higher dollar signs($) would be impacted by the 26 - 44 age group as the proportion of the population for all three geographic location is heavily weighted in this age group.


## Yelp
Before digging into the importance of variables for number of $'s in a restaurants page, it is important to understand what these symbols represent - price range for each symbol.

Dollar Signs ($)  | Ranges
------------------| -------------
$                 | Under $10
\$$               | $11 - $30
\$$$              | $31 - $60
\$$$$             | above $61



Given these values for each dollar sign it can be assumed with the income level distributions and age group distributions on the population analysis that a majority of the restuarants being evaluatd will be in the $$ range. And, according to this table we can see that is in fact the case for the restuarants being analyzed.

From this image, we can assume that the largest category will be Italian food based on the reviews recorded for this cuisine.

[Category Weight by Reviews](/Resources/CategoryvsReview.PNG)

Then, coupled with this image of restaurants, we an see that the Italian category is a pretty big contributor to the category distribution in this dataset with it being predominantly $$'s.

[Review Count by Price Range](/Resources/CategoryvsPrice.png)

Then, at this point, it would be good to see what type restaurants fit into $$ range restaurant. It should be noted that the images show all the restaurant categories in the Yelp data and the analysis will only consider the top five categories when ranking the importance of variables for prices.


## Tools
To execute the API, parsing, cleaning and modeling we used the following python packages:
* requests
* pandas
* matplotlib.pyplot
* json
* csv
* re
* reduce
* numpy
* warnings
* pathlib
* collections
* balanced_accuracy_score
* confusion_matrix
* classification_report_imbalanced
* sklearn.model_selection 
    * train_test_split
    * accuracy_score
    * confusion_matrix
    * classification_report_imbalanced
* Imblanced Learn
    * BalancedRandomForestClassifier


### Sources:   
* Census Data: <https://data.census.gov/table?q=+age+and+income&g=0400000US17,36,53>
* Zip Code Database:  <https://www.unitedstateszipcodes.org/zip-code-database/> 
* Metropolitan Areas: <https://www2.census.gov/geo/pdfs/reference/GARM/Ch13GARM.pdf>

