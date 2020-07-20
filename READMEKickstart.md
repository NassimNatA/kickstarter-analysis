# Kickstarting with Excel

## Overview 
This project produces deliverables by utilizing excel tools to analyze a large dataset of campaign attributes. The tools used include filtering to analyze data, visualization of desired attributes with pivot tables, and parsing data through excel commands to isolate desired information. These tools are being applied to draw conclusions on the overall campaign outcomes.

---
 ## Purpose 
The purpose of this project is to analyze the output of different campaigns in correlation to launch dates and funding goals for specifically the play subcategory. Additionally, the purpose of this output is to provide visualizations to better understand trends and to draw conclusions from the data for this desired variable. 
 
---
## Analysis and Challenges
### Analysis of Outcomes Based on Launch Date:
Analysis on the outcomes of the play campaigns (successful, failed, cancelled) in relation to launch date was done by first creating a Years column by utilizing the function YEARS() on the “Date Created Conversion” column. A pivot table was then generated with the “Parent Category” and “Years” set as filters, “Outcomes” as the Legend and Values, and “Date Created Conversion” set as the axis and grouped by months. A line chart when then generated to visualize the number of successful, failed, and canceled projects by month.  

![Theater_Outcomes_vs_Launch](Macintosh HD/Users/nassimnatalieataii/Desktop/Class Folder/CrowdFunding Analysis/Resources/Theater_Outcomes_vs_Launch.png)

---

### Analysis of Outcomes Based on Goals: 
 Analysis on the campaigns in relation to Outcomes based on Launch Date was done by first creating a table that listed Goals (containing groups of goal monetary amounts), vs. number of successful, failed, and canceled campaigns. In addition the table included the sum of the total campaigns (projects) to obtain the percentage breakdown in each monetary group (successful, failed, canceled). 

 1. To obtain the number of successful projects, below are two examples of codes was used to filter for successful campaigns, a desired monetary group, and for the “plays” category:
 
For monetary group Less Than 1000 
`=COUNTIFS(Kickstarter!F:F, "=successful", Kickstarter!D:D, "<1000", Kickstarter!R:R, "=plays")`

For monetary group 1000 to 4999
`=COUNTIFS(Kickstarter!F:F, "=successful", Kickstarter!D:D, ">=1000", Kickstarter!D:D, "<=4999", Kickstarter!R:R, "=plays")`

 2. To obtain the number of failed projects, below are two examples of codes was used to filter for successful campaigns, a desired monetary group, and for the “plays” category
For monetary group Less Than 1000 

`= COUNTIFS(Kickstarter!F:F, "=failed", Kickstarter!D:D, "<1000", Kickstarter!R:R, "=plays")`

For monetary group 1000 to 4999
`=COUNTIFS(Kickstarter!F:F, "=failed", Kickstarter!D:D, ">=1000", Kickstarter!D:D, "<=4999", Kickstarter!R:R, "=plays")`

3.  To obtain the number of canceled projects, below are two examples of codes was used to filter for successful campaigns, a desired monetary group, and for the “plays” category.

For monetary group Less Than 1000 
` =COUNTIFS(Kickstarter!F:F, "=canceled", Kickstarter!D:D, "<1000", Kickstarter!R:R, "=plays")`

For monetary group 1000 to 4999
`=COUNTIFS(Kickstarter!F:F, "=failed", Kickstarter!D:D, ">=1000", Kickstarter!D:D, "<=4999", Kickstarter!R:R, "=plays")`

4. The SUM function ` =SUM()`was then used to obtain the total number of project. The percentage for each outcome (successful, failed, canceled) was obtained by utilizing the ROUND function `=ROUND (_/_*100, 0)`


5. After obtaining all necessary information, a line graph was generated from the Goal columns and the three Outcome columns (successful, failed, canceled) to generate a overview of the campaign trends for plays. 

![Outcomes_vs_Goals](Macintosh HD/Users/nassimnatalieataii/Desktop/Class Folder/CrowdFunding Analysis/Resources/Outcomes_vs_Goals.png)

---
### Challenges and Difficulties Encountered: 
For deliverable 1, challenges included finding how to group a column in the pivot table (Date Created Conversion) to only include the Months in the pivot table. 
For deliverable 2, challenges included familiarizing with the COUNTIFS function to correctly include all necessary parameters, restrictions, and references for each cell. 

---

## Results
### What are two conclusions you can draw about the Outcomes based on Launch Date?
The first conclusion from the Outcomes based on Launch Date is that the successful theater  campaigns were most evident in the month of June, where there is a significant spike in the “successful” outcome. 
The second conclusion is that the failed theater campaigns had a spike in the month of October, when there were no canceled campaigns present. This may be a correlation to the reduced amount of canceled campaigns causing more failed outcomes to occur. 

### What can be concluded about the Outcomes based on Goals?
The first conclusion from Outcomes based on Goals is that only campaigns (plays) with less than $9999 in monetary goal were canceled. Any campaign greated than the $9999 expected monetary group were not canceled per the gray  trend in the graph. 
The second conclusion is that the percentage of failed campaigns rises when there is a dip in successful campaigns in the $25000 to $29999 monetary group. The assumption can be made that the spike in failed campaigns with goal of $25000 to $29999 is due to the decrease in successful campaigns in this monetary group. 

### Limitation of the dataset
Limitations of this dataset include non-specificity in the location variable. By separating by countries there is still a question of how localization affects the dataset within each country, in which regional data is not being represented. Additionally, another limitation in this dataset is conversion of currency between the different types available (AUD, SEK, etc.). Without normalization to a single currency type (like USD for example), there could be an inaccurate representation of monetary value in the dataset. 

### Other possible tables and/or graphs that can be created
Other possible tables and graphs that can be produced are to replicate the data above then separate by country to see if location has any effect on the success of failure outcomes of a campaign. Likewise, another possibility is to analyze the amount pledged to each campaign analyze cost-savings of the campaigns of goal vs. pledged and sort which campaigns (which subcategories) achieved sizeable gain or loss.  
