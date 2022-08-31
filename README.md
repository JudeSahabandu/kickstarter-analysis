# Kickstarting with Excel
---

## Overview of the project

Louise a playwriter wishes to raise funding for her play. In order to determine the best approach for raising funds, we are looking at a detailed analysis of past kickstarter data to ascertain the best way forward in terms of timing the fundraiser and setting the monetary goal.

## Purpose

The purpose of this report is to derive insight from 2 key analysis;

1. Determine fundraising outcomes based on the fundraiser launch month
2. Determine fundraising outcomes based on the monetary goal of the fundraiser

The above data points will provide insight into how to position our campaign launches based on time of year and the fund amount to raise, as factors within may indicate the success rate of the fundraising campaign.

## Analysis and challenges
---

### Analyzing outcomes based on launch date

For the purposes of the launch date analysis, a key requirement was to add a new column of data labeled "Years" based on the date created conversion tab. This element of data filtering was important to enable cleaner pivot table analysis.

![Years_Column_Creation](/Other/Year_Column_Creation.png)

The excel formula used to derive the year based data was `YEAR()`

Upon creation of the year tab, a pivot table was generated using the kickstarter data. Key inputs to the pivot table configuration are as follows;

1. Data filtering by Year and Parent category
2. Filtering Parent Category by the theater category
3. Setting the columns by the month of the year
4. Setting the outcomes column in descending order

This enabled the following format of the Pivot Table;

![Launch_Date_Outcome](/Other/Theater_Outcomes_Based_On_Launch_Dates.png) 

### Analyzing outcomes based on goals

The next analysis was to determine outcomes based on project goals, for this analysis it was required to use the `COUNTIFS` function.

An example of the formula used to determine the count of successful, failed and canceled campaigns is as follows; (formula can be found in cell B3 on the "Outcomes Based On Goals Worksheet)

`COUNTIFS(Kickstarter!$D:$D,">=1000",Kickstarter!$D:$D,"<=4999.99",Kickstarter!$F:$F,"successful",Kickstarter!$R:$R,"plays")` 

![Goal_Outcomes](/Other/Outcomes_Based_On_Goals.png)

### Challenges

The required analysis was straightforward. The ability to analyze requirement A (Outcomes Based On Launch Dates) through a pivot table was time saving. But, when considering requirement B (Outcomes Based on Goals) using the `COUNTIFS` function and the associated formatting was time consuming.

The key lesson learnt through structuring the data table for the outcomes based on goals chart was to use the correct inputs to ensure you can duplicate the data without having to format each individual cell formula. Placing the $ sign at the appropriate position within the formula helped to reduce rewriting most of formula when copying to other cells.

Using: `COUNTIFS(Kickstarter!$D:$D,">=1000",Kickstarter!$D:$D,"<=4999.99",Kickstarter!$H:$H,"successful",Kickstarter!$T:$T,"plays")`

Instead of: `COUNTIFS(Kickstarter!D:D,">=1000",Kickstarter!D:D,"<=4999.99",Kickstarter!H:H,"successful",Kickstarter!T:T,"plays")`

## Analysis of the data
---

### Outcomes based on launch date

![Outcomes_based_on_launch_date](/Resources/Theater_Outcomes_vs_Launch.png) 

- Throughout the year, failure of outcome is consistent. But, total campaigns launched between May to July increases causing the (%) propensity to fail decline in those months. 
- Based on the above, the best time to launch a campaign is during the early summer months. But regional based data may be required to verify this. (To determine if the inverse is true for Southern Hemisphere countries compared to Northern hemisphere countries).
- The analysis is very clear that the start and end of the year are the least favorable months to launch a successful campaign.

### Outcomes based on goals

![Outcomes_based_on_goals](/Resources/Outcomes_vs_Goals.png) 

- It is evident that campaigns with lower goals tend to have a higher success rate. Where almost 3 out of 4 campaigns ended up being successful where the campaign goal was below $5000.
- Half the total campaigns for plays tend to have a campaign goal below $5000, which may indicate most play writers are targeting a $5000 budget or are confident that a play can be funded under a budget of $5000. (Data derived through Total Projects Column in excel sheet)

## Limitations & recommended analysis
---

### Outcomes based on launch date

It is clear that success based on launch date is more evident in the months of May/June/July, which coincide with late Spring and early Summer in the Northern Hemisphere. It is important to determine if the inverse is seen in the Southern Hemisphere to understand the impact of seasonality and to further assess if any tropical regions have a consistent success rate throughout the year as they are not impacted by seasonality.

Recommendation - Launch campaign between May-July

Further Analysis - Determine if seasonality plays a factor in campaign launch

### Outcomes based on goals

Furthermore, understanding of regional impact is important. Success rate based on campaign goal may change by country, as disposable incomes will vary from country to country. For example, a country with lower disposable income may have a lower campaign success goal threshold when compared to that of a country with higher disposable income. This needs to be factored in when considering which region we intend to launch the campaign in.

Recommendation - Set campaign goal to $5000

Further Analysis - Determine if campaign goal threshold changes by country
