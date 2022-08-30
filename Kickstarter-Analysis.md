# Kickstarting with Excel

## Overview of Project

Louise, a playwriter wishes to raise funding for her play. In order to determine the best approach for raising funds, we are looking at a detailed analysis of past kickstarter data to ascertain the best way forward in raising the required funding.
---
## Purpose
---
The purpose of this analysis, is to derive insight from 2 key analysis;
---
1. Determine fundraising outcomes based on the fundraiser launch month
2. Determine fundraising outcomes based on the monetary goal of the fundraiser
---
The above, data points will provide insight into how to position our campaign launches based on time of year and the fund amount to raise, as factors within may indicate the success rate of the fundraising campaign.
---
## Analysis and Challenges
---
### Approach to Analysis
---
#### Analyzing outcomes based on launch date
---
For the purposes of the launch date analysis, a key requirement was to add a new column of data labeled "Years" based on the date created conversion tab. This element of data filtering was important to enable cleaner pivot table analysis.
---
Note: add Year_Column_Creation image
---
The excel formula used to derive the year based data was `YEAR()`
---
Upon creation of the year tab, a pivot table was generated using the kickstarter data. Key inputs to the pivot table configuration are as follows;
---
1. Data filtering by Year and Parent Category
2. Filtering Parent Category by the theater category
3. Setting the columns by the month of the year
4. Setting the outcomes column in descending order
---
This enabled the following format of the pivot table;
---
Note: add Theater_Outcomes_Based_On_Launch_Dates
---
#### Analyzing outcomes based on goals
---
The next analysis was to determine outcomes based on project goals, for this analysis it was required to use the `COUNTIFS` function.
---
An example of the formula used to determine the count of successful, failed and canceled campaigns is as follows; (formula can be found in cell B3 on the "Outcomes Based On Goals Worksheet)
---
`COUNTIFS(Kickstarter!$D:$D,">=1000",Kickstarter!$D:$D,"<=4999.99",Kickstarter!$F:$F,"successful",Kickstarter!$R:$R,"plays")`
---
Note: add Outcomes_Based_On_Goals
---
### Challenges
---
The required analysis was straightforward. The ability to analyze requirement A (Outcomes Based On Launch Dates) through a pivot table was time saving. But, when considering requirement B (Outcomes Based on Goals) using the `COUNTIFS` function and the associated formatting was time consuming.
---
The key lesson learnt through structuring the data table for the outcomes based on goals chart was to use the correct inputs to ensure you can duplicate the data without having to format each individual cell formula. Placing the $ sign at the appropriate position within the formula helped to reduce rewriting most of formula when copying to other cells
---
Using: `COUNTIFS(Kickstarter!$D:$D,">=1000",Kickstarter!$D:$D,"<=4999.99",Kickstarter!$H:$H,"successful",Kickstarter!$T:$T,"plays")`
---
Instead of: `COUNTIFS(Kickstarter!D:D,">=1000",Kickstarter!D:D,"<=4999.99",Kickstarter!H:H,"successful",Kickstarter!T:T,"plays")`
---
### Analysis of the data
---
#### Outcomes Based on Launch Date
---
- Throughout the year, failure of outcome is very consistent. Although, total campaigns launched between May to July increases causing the propensity (%) to fail drop. 
- Based on the above, the best time to launch a campaign is during the early summer months. But regional based data may be required to verify this. (To determine if the inverse is true for Southern Hemisphere countries compared to Northern hemisphere countries).
- The analysis is very clear that the tail end and start of a year are the least plausible times to launch a successful campaign.
---
#### Outcomes Based on Goals
---
- It is evident that campaigns with lower goals tend to have a higher success rate. Where almost 3 out of 4 campaigns ended up being successful where the campaign goal was below 5000.
- Half the total campaigns for plays tend to have a campaign goal below 5000, which may indicate most creators are targeting a 5000 budget or are confident that a play can be funded with a budget of 5000.
---
### Limitations and Recommended Analysis
---
#### Outcomes based on launch date
--- 
It is clear that success based on launch date is more evident in the months of May/June/July, which coincide with late Spring and early Summer in the Northern Hemisphere. It is important to determine if the inverse is seen in the Southern Hemisphere to understand the impact of seasonality and to assess if the tropical regions cave a consistent success rate as they are not impacted by seasonality.
---
#### Outcomes based on goals
---
Further understanding of regional impact is important. Success rate based on campaign goal will change by country, as disposable incomes will vary from country to country. For example, a country with lower disposable income may have a lower campaign success goal threshold when compared to that of a country with higher disposable income.
