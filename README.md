<h2> <p align=center> Analysis of Kickstarter Crowdfunding Campaigns </p> </h3>

<h3> <p align=center> Background  </p> </h3>

Crowdfunding is the practice of funding a project or a venture by raising small amounts of money from a large number of people. Kickstarter is one of the most popular online crowdfunding platforms for creative projects. The creators set a funding goal and a deadline for their project funding campaign. If the project gathers enough pledge by the backers to meet their funding goal before the deadline, the project gets funded successfully.

<h3> <p align=center> Purpose </p> </h3>

A promising playwright Louise held a Kickstarter crowdfunding campaign for her new play 'Fever'. The campaign came close to its fundraising goal in a short amount of time. Lousie requires a better understanding of how different campaigns performed in relation to their launch dates and their funding goals. 

This analysis is focused on **finding if campaign outcomes have any correlation with their launch dates and their funding goals**.

<h3> <p align=center> Project Overview </p> </h3>

The Kickstarter sample dataset being used for this analysis contains the key information for campaigns in 14 columns and a little over 4000 records. In order to analyze this dataset for the outcomes based on Launch date and outcomes based on Goals, the dataset was cleaned, organized and prepared as described below. 

<h4> <p align=left> Data Cleaning and Data Preparation </p> </h4>

* The data under consideration was verified for absence null or blank values.
* The data types were checked for relevance and consistency in each column.
* The dates were converted from unix date format to short date format into a separate column called 'Date Created Conversion'. 
* Next, only the years were extracted from the 'Date Created Conversion' column into a separate column 'Years' using YEAR() function in Excel. The 'Years' column was later used for creating Pivot table based on Launch date.
* Since we were only focusing on the specific campaign type, the text in 'Category and subcategory' column was split into two columns using 'Text to Columns' tool in Excel.

The cleaned and prepared dataset was then analyzed in Excel using Pivot table and other Excel functions. The resulting data was visualized using line charts to discover any trends. This analysis has been discussed in detail below.

<h3> <p align=center> Analysis </p> </h3>

This analysis was performed in two parts:

1. Analysis of Outcomes Based on Launch Date

To analyze the relationship between campaign outcomes with their launch date, a Pivot table was created. The rows were based on Years column and contained the outcome data by months for successful, failed and canceled campaigns.
Parent Category was added to filter along with Years. Pivot table was filtered to show outcomes for only 'Theater' category. The data was available for the total of 1369 'Theater' campaigns.

<img width="437" alt="Pivot_Table_Outcomes_by_Launch_Date" src="https://user-images.githubusercontent.com/90424752/138800245-5673745f-a833-430b-9ebf-0c8c7cd7ab63.png">


2. Analysis  of Outcomes Based on Goals

The second analysis was performed using the COUNTIFS function to filter the desired data from Kickstarter dataset. The outcome data for campaigns falling into different goal brackets but only pertaining to 'play' subcategory, was filtered into the table. The total number of projects and percentages of successful, failed and canceled outcomes were then calculated. The visualization and observations for this analysis have been discussed in detail in the following section.

<img width="1202" alt="Table_Outcome_by_Goals" src="https://user-images.githubusercontent.com/90424752/138800280-223b7fd3-1dea-499d-b1dc-1a2e1e757373.png">


 <h3> <p align=center> Analysis of Outcomes Based on Launch Date  </p> </h3>
 
 A few observations were brought into light by visualizing Number of Outcomes vs. Launch date in the form of line chart:

![Theater Outcomes by Launch date](https://user-images.githubusercontent.com/90424752/138645504-a13454cf-9d68-463f-b3db-5b6131773b60.png)

<h4> <p align=left> Observations </p> </h4>

* The graph shows that the highest number of successful campaigns were launched in the month of May, followed by June.
* It can also be observed that June, July and October have approximately the same number of failed campaigns.


<h3> <p align=center> Analysis of Outcomes Based on Goals </p> </h3>

This chart visualizes Outcomes vs. Goals for our second analysis.

![Outcomes based on Goal](https://user-images.githubusercontent.com/90424752/138645589-0bec9a29-83d9-472a-9eb3-672cb078ccee.png)

<h4> <p align=left> Observations </p> </h4>

* The lowest goal amount range (< $1000) shows the highest percentage (76%) for successful campaigns. 
* The percentage of successful outcomes shows consistent decline as the goal amount range increase upto $35,000 range. From $35,000 to $44,999 the outcomes show sudden increase in percentage which again plummets down to 0% as the goal amounts go in the further ( >= $45,000 to <= $49,999) range.

<h3> <p align=center> Challenges and Difficulties Encountered </p> </h3>

* Filtering out data with the help of COUNTIFS was a little trickier than filtering data with filters. I had to be cautious using formula with more number of parameters and conditions as it got a bit tedious to debug. However it gave me a table of just numbers which could be easily populated on the graph to show trends.
* The second analysis was based on single parameter - percentage. The percentages can be ambiguous and misleading as it does not take into account the actual number data points. 
* This analysis is not backed by any statistical analysis.

<h3> <p align=center> Limitations of the Dataset </p> </h3>

* The dataset holds a little over 4000 records for 9 categories and aboout 41 subcategories. That leaves us with very little data to analyze for some subcategories.
* The dataset is limited (small sample) and a bit outdated, the latest data being 4 years old.


<h3> <p align=center>  Recommendations </p> </h3>

* Based on the above analysis, no concrete recommendations can be made, as it is not backed by any statistical analysis, however there is room for further         analysis.
* To make the above analysis thorough, following additional analyses could be performed:

  * **Theater Outcomes by Launch Date:**
    1. Additional data that is also more recent ( during years 2018 to 2021) could either bolster the findings from the line chart or could lead to slight change     in the observed trends.
    
  * **Outcomes Based on goals**
    1. The statistical analysis of successful and failed goals in terms of central tendancies as well as spread (standard deviation, Quartiles) will provide            additional insights into the data. Box and whiskers plot will be useful to understand the data distribution.

  * **Additional Analyses:**
    1. Additionally the dataset could be analyzed for the outcomes vs. the duration for which the campaign was held to uncover any correlation between them.
    2. Outcomes vs. Launch dates could also be analyzed country wise to discover any country specific trends that could prove valuable for project creators.
