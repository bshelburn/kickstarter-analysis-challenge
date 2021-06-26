# Kickstarter Campaign Funding Analysis
---
## Overview
Performed an analysis for Louise comprised of the outcome and success of other Kickstarter campaigns based on both Launch Date and their associated goals.   The Launch Date analysis data set was focused on the Parent Category of Theater which includes Plays, Musicals, and Spaces while the analysis of Goals for funds raised was specific to the Plays subcategory.   

### Purpose
This analysis was the result of Louise coming close to her Kickstarter goal for her Play Fever in a short amount of time and wanting to see how other initiatives fared compared to her results.

## Analysis & Challenges
### Analysis of Outcomes Based on Launch Date
![Theater_Outcomes_vs_Launch](https://user-images.githubusercontent.com/84201082/123518244-077abf00-d673-11eb-8c36-0579e6c78bab.png)
Utilizing the Kickstarter data we first converted the Date Created column to show only the year of campaign launchg by using the = YEAR() function: =YEAR([@[Date Created Conversion]]).   A Pivot Table was placed in the newly created Theater Outcomes by Launch Date sheet. 

Both the Parent Category and newly converted Years columns were used filters for the data set.   The Outcomes column was placed into the Columns portion of the pivot table, the Date Created was designated as the table Rows, and Outcomes was again placed in the Values.

### Analysis of Outcomes Based on Goals
![Outcomes_vs_Goals](https://user-images.githubusercontent.com/84201082/123518280-2ed18c00-d673-11eb-8fe1-9d1e1c69aa04.png)

### Challenges and Difficulties Encountered 
