# Kickstarter Campaign Funding Analysis
---
## Overview
Performed an analysis for Louise comprised of the outcome and success of other Kickstarter campaigns based on both Launch Date and their associated goals.   The Launch Date analysis data set was focused on the Parent Category of Theater which includes Plays, Musicals, and Spaces while the analysis of Goals for funds raised was specific to the Plays subcategory.   

### Purpose
This analysis was the result of Louise coming close to her Kickstarter goal for her Play Fever in a short amount of time and wanting to see how other initiatives fared compared to her results.

## Analysis & Challenges
### Analysis of Outcomes Based on Launch Date
![Theater_Outcomes_vs_Launch](https://user-images.githubusercontent.com/84201082/123518244-077abf00-d673-11eb-8c36-0579e6c78bab.png)
Utilizing the Kickstarter data we first converted the Date Created column to show only the year of campaign launchg by using the = YEAR() function: Ex. =YEAR([@[Date Created Conversion]]).   A Pivot Table was placed in the newly created Theater Outcomes by Launch Date sheet. 

Both the Parent Category and newly converted Years columns were used filters for the data set.   The Outcomes column was placed into the Columns portion of the pivot table, the Date Created was designated as the table Rows, and Outcomes was again placed in the Values with a Count assignment.  The Outcomes columns were limimted to only Successful, Failed, and Canceled which ommited the Live category.   

The Parent Category filter was then set on Theater which included the subcategories of Plays, Musicals, and Spaces.   Our analysis included all years split by month which required no modification of the filter.   Results were the organized in descending order which placed Successful in the left most results column followed by Failed and Canceled.

Once the data set was checked for accuracy against the original data set the table was selected and a line Chart with Markers was inserted into the same worksheet and given the title of "Theater Outcomes Based on Launch Date" (inserted above) showing the results of the projects by month.

### Analysis of Outcomes Based on Goals
![Outcomes_vs_Goals](https://user-images.githubusercontent.com/84201082/123518280-2ed18c00-d673-11eb-8fe1-9d1e1c69aa04.png)
In the same Workbook and new worksheet was created and called Outcomes Based on Goals.   Metrics to be measured were count of Number Successful, Number Failed, Number Canceled, Total Projects, Percentage Successful, Percentage Failed, Percentage Canceled.   These were split into 12 specific fund buckets shown in the Goal column of the worksheet and X axis of the chart above.

To total the number for each category and funding bucket multiple =COUNTIFS() functions were used depending on both the outcome of the initiative and which funding bucket was being analyzed: Ex. =COUNTIFS(Kickstarter!$F:$F,"Successful",Kickstarter!$O:$O,"plays", Kickstarter!$D:$D, "<1000"), =COUNTIFS(Kickstarter!$F:$F,"canceled",Kickstarter!$O:$O,"plays", Kickstarter!$D:$D, ">=30000", Kickstarter!$D:$D, "<=34999"), =COUNTIFS(Kickstarter!$F:$F,"failed",Kickstarter!$O:$O,"plays", Kickstarter!$D:$D, ">=50000").   The results were confirmed to be correct and checked against the source data.

The =SUM() function was used for the totals column which included the 3 categories of Successful, Failed, and Canceled: Ex. =SUM(B2:D2).   The percentage of the outcomes was calculated by dividing the counted outcome & funding bucket amount by the total results and converting the 3 percentage columns to show the decimals as a percentage: Ex. =B2/E2

The funding buckets were selected along with the percentage results of the spreadsheet and a Line Graph without Markers labeled Outcomes Based on Goals was inserted into the Outcomes Based on Goals worksheet with the funding bucket amounts on the X axis and the result categories on the Y axis. 

### Challenges and Difficulties Encountered
Difficulties faced were verifying the data points given such a large data set.   In order to make sure the code written was returning the corrct values a manual spot check was neccesary.   A big cahllenge was the discovery to include the constrict of plays within the =COUNTIFS formulas since the Outcomes Based on Goals was specific to that subcategory.   Results were not matching no matter how the formula was written before disovered. Rereading the scope of the Module several times finally revealed the key to success.

In addition, the use of using the ">=" instead of ">" or "<" outside of the first and last funding bucket category led to numbers being slightly off as some numbers fell firectly on 1000 or 50000, placing them in the wrong bucket.

## Results
