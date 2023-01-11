# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 1: How might we use historical weather data to anticipate demand for water sports activities so to better plan staffing needs and provide a positive experience for our customers? 

### Executive Summary 

Happy Water House (HWH), an outdoor water sports centre in Singapore, is adapting its business to the weather conditions in the region by introducing indoor water sports activities. HWH used historical weather data to anticipate demand for water sports activities and plan staffing needs. HWH expects higher customer numbers at its outdoor sports centre during months with low rainfall, few rainy days, high sunshine duration, and low surface air temperature, and expects the number of customers at both its outdoor and indoor sports centres to be positively correlated with the number of international visitors to Singapore. Based on these findings, HWH is suggested to increase staff at its outdoor sports centres in February and June, reduce staff at its outdoor sports centres in November and December, and encourage staff to clear annual leave in February, April, and September based on the anticipated number of international visitors.

### Background 

Weather conditions can have a significant impact on the business of outdoor water sports centres. According to a report from [Channel NewsAsia](https://www.channelnewsasia.com/singapore/safety-sea-monsoon-season-3138611), local outdoor water sports centres are cutting their operating hours and reducing activity zones in view of the monsoon season which typically lasts from December to early March, and from June to September. A [Forbes](https://www.forbes.com/sites/jimfoerster/2019/06/28/five-industries-that-rely-on-weather-to-make-decisions/?sh=47ccc5247927) report mentioned that the incorporation of weather forecasts into business plans can help optimise staffing and increase profitability for selected industries by allowing for better planning and preparation.

### Problem Statement 

Happy Water House (HWH), an outdoor water sports centre located at East Coast Park in Singapore, recognises the need to adapt its business to the weather conditions in Singapore. To minimise the risk of losing customers due to unfavourable weather, such as heavy rain or high temperatures, HWH will introduce indoor water sports activities options to complement their outdoor water sports offerings.

This project aims to explore how might HWH use historical weather data to anticipate demand for water sports activities so to better plan staffing needs and provide a positive experience for all customers. HWH expects the following customer patterns at their outdoor and indoor sports centres:

***Outdoor sports centre***: higher customer numbers during months with low rainfall, few rainy days, high sunshine duration, and low surface air temperature.

***Indoor sports centre***: higher customer numbers during months with high rainfall, many rainy days, low sunshine duration, and high surface air temperature.

In addition to weather conditions, HWH expects that the number of customers at both their outdoor and indoor sports centres will also be positively correlated with the total number of international visitors to Singapore in a given month. This is because a significant portion of their past customers are tourists.

### Data Dictionary

All datasets were sourced from [Data.gov.sg](https://data.gov.sg/). 

[Data.gov.sg](https://data.gov.sg/) was first launched in 2011 as the Singapore government's one-stop portal to its publicly-available datasets from 70 public agencies. To date, more than 100 apps have been created using the government’s open data.

***Historical Weather data***

|Feature|Type|Dataset|Description|
|---|---|---|---|
|total_rainfall|float|rainfall-monthly-total|Monthly total rainfall recorded in mm(millimeters) from 1982 to 2022|
|rainy_days|integer|rainfall-monthly-number-of-rain-days|Monthly total number of rain days from 1982 to 2022. A day is considered to have “rained” if the total rainfall for that day is 0.2mm or more.|
|sunshine_hrs|float|sunshine-duration-monthly-mean-daily-duration|Monthly mean sunshine hours in a day from 1982 to 2022|
|air_temp|float|surface-air-temperature-monthly-mean-daily-minimum|Monthly mean daily minimum surface air temperature from 1982 to 2022|

***Historical Singapore's International Visitor Arrivals data***

|Feature|Type|Dataset|Description|
|---|---|---|---|
|visitor_arrival|integer|total-visitor-international-arrivals-monthly|Monthly international visitor arriavls to Singapore from 1978 to 2015|

### Summary of Analysis

We examined Singapore's historical weather data to identify months of the year with high and low rainfall, many and few rainy days, high and low sunshine duration, and surface air temperature. The historical Singapore's International Visitor Arrivals data was also examined to determine months of high and low tourist arrivals since a significant portion of HWH's past customers are tourists.

***Data Pre-processing***

First, we checked for any issues such as missing values or inconsistent data types in all datasets. Next, we merged the datasets into a single dataframe for ease of analysis, using the common 'month' column as a reference. We also dropped any data from 2016-2022 as the Singapore International Visitor Arrivals dataset does not have data for these years. Finally, to make it easier to analyse the data by year and month, we splitted the 'month' column into two new columns of year and month.

***Analysis***

We plotted a **correlation matrix (heatmap)** to identify any relationships among the different categories. These are the main findings:

- Strong positive correlation between year and visitor_arrivals
- Strong negative correlation between total_rainfall and sunshine_hrs
- Strong positive correlation between total_rainfall and rainy_days
- Strong negative correlation between rainy_days and sunshine_hrs

We plotted a **Histogram Subplots** to visualise distribution of selected features. These are the main findings:

- Normally distribution of rainy days, sunshine hours and air temperature datasets.
- Right-skewed distribution of total rainfall and visitor arrivals datasets.

We plotted **Boxplot Subplots** to identify outliers of selected features. These are the main findings:

- Outliers in the datasets of "total_rainfall", "sunshine_hrs" and "visitor_arrivals".
- No outliers in the datasets of "rainy_days" and "air_temp".

We plotted **Pairplots** to have an overview of correlations between all numeric features and Scatter plots to deep-dive into relationships between selected features. These are the main findings:

- Total rainfall (mm) increases as the sunshine hours (Hours) decreases.
- Total rainfall (mm) increases as the number of rainy days also increases.
- Sunshine hours increases as the number of rainy days decreases.

We plotted **Bar Plots with Line Chart** to study the trend of selected features between 1982 to 2015. Our findings shows that on average,

- Total rainfall and rain days are the highest in the months of November and December while lowest in the month of Feburary and June.
- Sunshine durations is the lowest in the months of November and December while highest in the month of Feburary and June.
- Surface air temperature is the highest in the months of May and June while lowest in months of January and December.
- International visitor arrivals is the highest in the months of July, August and December while lowest in the month of Feburary, April and September.

### Conclusions/Recommendations

Outdoor water sport centers can provide unique experiences for visitors, but unfavourable weather can ruin this experience. By using historical weather data to anticipate demand, Happy Water House (HWH) aims to better plan staffing needs and provide a positive experience for all customers. In this way, HWH can stay profitable and ahead of the competition.

Considering all above findings from historical weather data, HWH is suggested to: 

- **Increase staff at its Outdoor Sports Centres** in the month of February and June in anticipation of lower rainfall, fewer rainy days, higher sunshine duration, and lower surface air temperature.

- **Reduce staff at its Outdoor Sports Centres** while increasing staff at its Indoor Sports Centres in the month of November and December in anticipation of higher rainfall, higher rainy days, lower sunshine duration, and higher surface air temperature.

- **Encourage staff to clear their annual leave** in the month of February, April and September in anticipation of lower international visitor arrivals while scaling number of staff in the month of July, August and December in anticipation of higher international visitor arrivals. 

|Month|Sports Centre with higher Staffing needs|Visitor Arrivals  
|---|---|---|
|January|-|-|- 
|February|Outdoor|Low ; Leave Clearance 
|March|-|-
|April|-|Low ; Leave Clearance 
|May|-|-
|June|Outdoor|-
|July|-|High ; No Leave Clearance 
|August|-|High ; No Leave Clearance 
|September|-|Low ; Leave Clearance 
|October|-|-
|November|Indoor|-
|December|Indoor|High ; No Leave Clearance 

***Future Studies***

1. To consider the potential shift in weather patterns over a period of more than 30 years (1982-2015) by analysing weather data at the decade level (1982-1992, 1993-2003) as this may misrepresent anticipated demand.

2. To gather historical visitor expenditure data at HWH and examine correlations with existing datasets to understand the factors that drive the most spending.  