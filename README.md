# Yelp Metro US Analysis

## Objective
The objective of this project is to understand the different variables that impact the price for a given restaurant. To capture the differing demographic tendencies we looked at Washington State for the west coast, Illinois for the midwest and New York for the east coast. The project was aimed to understand how different demographics impacted the pricing for restaurants in their respective metropolitan areas.

In this analysis, we will aim to look at the combined analysis which will look at the west coast(WC), midwest (MW) and east coast(EC) in a single analysis as well as look at each geographic location on their own.

## Data Sources
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

### Combined Analysis
The combined analysis aimed to understand the themes present for the entire dataset that include WC, EC and MW.

This initial eploratory visual let us know that the number of restaurants were heavily weighted on the EC/New York, which let us know that a simple logistic regression would not paint the correct picture for us in understanding impacts the pricing rank of a restaurant on Yelp.

[State V. Reviews Count](/Resources/StateVReviewCounts.PNG)


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

