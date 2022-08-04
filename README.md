# Kickstarting with Excel

## Overview of Project

### Purpose

The purpose of this analysis was to provide the client, Ms. Louise, with information on theater Kickstarters so that she could be successful in funding her own plays. After an initial success with her own Kickstarer campaign, the client wanted to see how launch dates and funding goals affected theater Kickstarters. Analyses were performed using categorical outcome data (success, failure, cancelation) to assess what impact, if any, launch date and funding goal had.

## Analysis and Challenges

Analysis of this data was done in MS Excel, primarliy using Pivot Table and data visualization functionality. More comprehensive explanation of methods may be found by subcategory below:

### Analysis of Outcomes Based on Launch Date

The month each campaign was launched in was extracted from Kickstarters launched_at data, which had been converted into standard datetime format from its UNIX timestamp. Addtionally, the Kickstarter Category and Subcategory variable with split into discrete, separate category and subcategory variables to allow for more precise filtering. The dataset for this analysis was filtered on the Category level, for "theater", which contained several subcategories. The Kickstarter data containted an outcomes categorical variable, which had successful, failed, cancelled, and live categories. Live campaigns were excluded from this analysis.

A Pivot Table was created using the dataset, with month from the launch date used for rows and the outcome categories used for columns. The results were based on a count of outcomes, which effectively provided a row count for each cell. The Pivot Table was then used to generate a line chart tracking outcomes by month.

### Analysis of Outcomes Based on Goals

This analysis was based on the same data as above. Bins for goal funding amount were created in increments of $5000, excepting the lower bounds (<1000) and upper bounds (>50,000). This analysis was limited to the subcategory plays, a subset of the theater category from the first analysis. Excel's COUNTIFS function was used to calculate the count for each successful, failed, and cancelled Kickstarter for each of the goal bins. The total number of projects per bin was found with SUM, and then each category was divided by the total to get the percentage successful, failed, and cancelled projects per bin. This data was then used to generate a line graph tracking the percentage of outcomes based on the goal bins.

### Challenges and Difficulties Encountered

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

- What can you conclude about the Outcomes based on Goals?

- What are some limitations of this dataset?

- What are some other possible tables and/or graphs that we could create?
