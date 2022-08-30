# Kickstarting with Excel
---
## Overview of the project

Loise a playwriter wishes to raise funding for her play. In order to determine the best approach for raising funds, we are looking at a detailed analysis of past kickstarter data to ascertain the best way forward in raising the required funding.

## Purpose

The purpose of this analysis is to derive insight from 2 key analysis;

1. Determine fundraising outcomes based on the fundraiser launch month
2. Determine fundraising outcomes based on the monetary goal of the fundraiser

The above, data points will provide insight into how to position our campaign launches based on time of year and the fund amount to raise, as factors within may indicate the success rate of the fundraising campaign.

## Analysis and Challenges
---
### Analyzing outcomes based on launch date

For the purposes of the launch date analysis, a key requirement was to add a new column of data labeled "Years" based on the date created conversion tab. This element of data filtering was important to enable cleaner pivot table analysis.

![Years_Column_Creation](/Other/Year_Column_Creation.png)

The excel formula used to derive the year based data was `YEAR()`

Upon creation of the year tab, a pivot table was generated using the kickstarter data. Key inputs to the pivot table configuration are as follows;

1. Data filtering by Year and Parent Category
2. Filtering Parent Category by the theater category
3. Setting the columns by the month of the year
4. Setting the outcomes column in descending order

This enabled the following format of the Pivot Table;
