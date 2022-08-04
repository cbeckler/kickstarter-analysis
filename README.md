# Kickstarting with Excel

## Overview of Project

### Purpose

The purpose of this analysis was to provide the client, Ms. Louise, with information on theater Kickstarters so that she could be successful in funding her own plays. After an initial success with her own Kickstarer campaign, the client wanted to see how launch dates and funding goals affected theater Kickstarters. Analyses were performed using categorical outcome data (success, failure, cancelation) to assess what impact, if any, launch date and funding goal had.

## Analysis and Challenges

Analysis of this data was done in MS Excel, primarliy using Pivot Table and data visualization functionality. The Excel document used to process data may be found [here](https://github.com/cbeckler/kickstarter-analysis/blob/main/Kickstarter_Challenge.zip).

More comprehensive explanation of methods may be found by subcategory below:

### Analysis of Outcomes Based on Launch Date

The month each campaign was launched in was extracted from Kickstarters launched_at data, which had been converted into standard datetime format from its UNIX timestamp. Addtionally, the Kickstarter Category and Subcategory variable was split into discrete, separate category and subcategory variables to allow for more precise filtering. The dataset for this analysis was filtered on the Category level, for "theater", which contained several subcategories. The Kickstarter data containted an outcomes categorical variable, which had successful, failed, cancelled, and live categories. Live campaigns were excluded from this analysis.

A Pivot Table was created using the dataset, with month from the launch date used for rows and the outcome categories used for columns. The results were based on a count of outcomes, which effectively provided a row count for each cell. The Pivot Table was then used to generate a line chart tracking outcomes by month. The Pivot Table may be seen below:

![Outcomes Pivot Table](https://github.com/cbeckler/kickstarter-analysis/blob/main/outcome_pivot_table.png)

### Analysis of Outcomes Based on Goals

This analysis was based on the same data as above. Bins for goal funding amount were created in increments of $5000, excepting the lower bounds (<1000) and upper bounds (>50,000). This analysis was limited to the subcategory plays, a subset of the theater category from the first analysis. Excel's COUNTIFS function was used to calculate the count for each successful, failed, and cancelled Kickstarter for each of the goal bins. The total number of projects per bin was found with SUM, and then each category was divided by the total to get the percentage successful, failed, and cancelled projects per bin. This data was then used to generate a line graph tracking the percentage of outcomes based on the goal bins.

The Excel calculations may be seen below:

![Outcomes Goal Bins Analysis](https://github.com/cbeckler/kickstarter-analysis/blob/main/outcomes_goals.png)

### Challenges and Difficulties Encountered

While the analyst did not encounter any challenges with this report, there are possible difficulties that could be encountered. When converting dates from UNIX timestamps, if the equation for conversion from seconds or the Epoch date is typed in incorrectly, it may throw off the conversion--and depending on the typo, may do so in a way that is subtle enough to not be easily caught (being off by only a few days, for instance). Having the wrong launch date could throw off the outcomes by launch date analysis.

A problem that could occur for the outcomes based on goals analysis could be confusion between the COUNTIF and COUNTIFS functions, the first of which allows for only a single condition. Any typos in the conditions for bins could also result in an inaccurate count, such as a count for goals $5000-8999 instead of $5000-9999.

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

It is easiest to draw conclusions from the data visualization:

![Theater Outcomes Based on Lauch Date line chart](https://github.com/cbeckler/kickstarter-analysis/blob/main/Resources/Theater_Outcomes_vs_Launch.png)

The first conclusion is that the highest number of theater Kickstarter successful campaigns occurs with May launch dates. There is a sharp increase between April and May campaigns, which then decrease gradually until returning to April levels around August, so the ideal time frame in which to launch theater campaigns may be late Spring and early Summer.

Failed campaigns are much more level across the year, but peak in October. However, the month in which failed and successful campaigns have the closest ratio to each other is December, with what looks to be close to a 50/50 split. Based on both overall number of failures and highest proportion of failures, it appears that October and December are the top two months to be avoided for theater campaign launches.

- What can you conclude about the Outcomes based on Goals?

![Outcomes Based on Goals line chart](https://github.com/cbeckler/kickstarter-analysis/blob/main/Resources/Outcomes_vs_Goals.png)

Generally, the percentage of successful campaigns remains highest for play Kickstarters under $15,000. The only other bracket in which successes are proportionally higher than failures are in the $35,000 to $44,999 range. However, the N for projects in this bucket is 17, versus nearly 1000 in the <$15,000 range. It is possible that it is simply a quirk of the data because of the small sample. With this in mind, the analyst's recommendation would be to keep play Kickstarter goals at $15,000 or less.


- What are some limitations of this dataset?

One of the limitations of this dataset is a relatively small size. It is only 4114 rows, which shrinks further to 1393 when limiting to the theater category. Given that by 2019, Kickstarter had launched over 469,000 projects, this is too small a sample to be likely to provide accurate insights, even if the data was collected via random sampling. Furthermore, the data provided only goes up to campaigns launched in 2017. Since that is at this point 5 years ago, the data is likely too far out of date to provide accurate information to a client seeking to launch a current campaign.

This issue is compounded by the COVID-19 crisis, which has hugely impacted the theater sector since 2020. Conclusions for a 2022 theater Kickstarter campaign from this data are to be considered with caution.

- What are some other possible tables and/or graphs that we could create?

A table that may be useful would be an analysis of average donation amount by month. It is possible the amount people are willing and able to give may be affected by time of year--perhaps the high rate of failure for campaigns launched in December may have been impacted by people spending their discretionary income on Christmas shopping. It would also be possible to create a line chart to see trends at a glance based on such an analysis.

The analyst would also recommend a line chart tracking successess and failures not by month, but over time continuously. While the averages of successes and failures by month is useful, it would be good to see if trends changed over time--is May 2017 equally as strong as May 2009?
