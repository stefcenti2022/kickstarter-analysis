# Kickstarter Campaign Analysis

## Overview of Project

Louise is an upcoming playwright that wants to start a fundraising campaign to fund her play, "Fever". Her budget is estimated to be around $12K and she would like more information about what she can do to ensure her campaign will be successful.

This analysis will attempt to sift through thousands of previous fundraising campaigns to determine what makes a successful campaign.  We will include charts and tables to show trends in the data to present the data in a comprehensible format.

---

## Analysis and Challenges

### Performance Analysis

### Analysis of Outcomes Based on Launch Date
[TODO: Explain how this analysis was performed and include code or other images if they can help.]

![Theater_Outcomes_vs_Launch.png](./resources/Theater_Outcomes_vs_Launch.png)

---

### Analysis of Outcomes Based on Goals

#### Performance Details
This analysis was performed by setting up specific ranges of funding goals for the "plays" subcategory within the "theater" parent category.  To do this I first created a new worksheet showing the breaking down the goals in ranges of $5,000.  Anything goal less than $1,000 or greater than $50,000 were included as separate goals to include all goals at the upper and lower ranges.

To get the total numbers within each range, I useed the COUNTIFS function as follows:
  =COUNTIFS(Kickstarter!F:F, "successful", Kickstarter!R:R,"plays", Kickstarter!$D:$D, "<1000")
In this example, the data will be pulled from the Kickstarter table and will be added to the total if the outcome is successful, the subcategory is a play and the goal is in the range specified. In this case, any goal less than $1,000 will be included. I used this function for failed and canceled outcomes to fill those columns. 

The rest of the table includes the Total number of projects and the percentage of succesful, failed and canceled plays for each goal range.  The total used the SUM function and the percentages were calculated using the ROUND function to divide each outcome by the total number of projects in each range.

Here is an image of the table created which will be referenced below when describing what I found from the pivot table and line chart:

![Outcomes_Including_Totals.png](./resources/Outcomes_Including_Totals.png)

Once this table was created, I used this smaller dataset to create a Pivot Table and Line Chart to only reflect the percentages for each outcome based on the goal ranges.

#### Conclusions
From the line chart below we can see the following information:

- The most successful funding raising efforts were for plays that had a fundraising goal of less than $1000. This is understandable, since it is a very low amount and would need less backers to reach the goal.

- The least successful projects where in the range of 45,000 to 49,000. This also makes sense as the more money that is needed the harder it will be to find the backers to support it. 

- However, plays with a goal of greater than $50,000 are shown to be more successful even though this could be a significantly higher goal to reach as it is unlimited.  If we go back to the original table that was used to create this chart we can see that there was only one play with a funding goal in the range of $45-$49K. Since that play failed the success rate would be 0, whereas, even though most plays with a goal over $50K had a lot more failures, it does have 2 that were successful which is enough to show a significant difference in the line chart.

- Noticing this now, it seems that the pivot table may be more informative if it included the total number of projects. If I have some time at a later date, I can add this column so the previous table will not be needed in this document.

- In the range of $35K to $44.9K there are quite a few successful projects yet in the ranges just below this level, i.e. $25K to $34.9K there was a high failure rate. There are no significant data in this part of the analyis to indicate why but the analysis by launch date may show something when I go back to anyalize that part.  [TODO: come back here and update once the analysis by Launch Date is evaluated.]

![Outcomes_vs_Goals.png](./resources/Outcomes_vs_Goals.png)

---

### Challenges and Difficulties Encountered
I had a few challenges to work around in order to get the desired results.

- To start, I had the wrong data after completing the modules.  Most likely this was due to some editing I did that either overwritten data or removed it.  After starting with a new download of Kickstarter data and running through the modules again the line chart for Outcomes Based on Launch Date macthed.

- In module 1.5.2 Measures of Spread, the table for the Descriptive Statistics tab was correct for the Goals and for the mean, median and standard deviation of pledged amounts, however, the Quartiles were off only for the Pledged cells by a small margin.  After comparing data with the original sheet for quite a while, I noticed I forgot to use the .EXC part of the Quartile function.

I am still new to excel and it has been a long time since I took statistics so I need to understand this better still but it makes sense that before I excluded data the values were only off slightly. Once I did exclude it, the values matched the exercise exactly. Later, I noticed this was specified but in a rush to redo the modules I missed this part of the function.

For Deliverable 2, I ran into a couple of issues.

  - At first I was not getting the correct data for the inital pivot table to create the correct line chart.  In the end, I forgot to add the condition to check for only "plays". Once I added this condition to each of the cells, the data matched perfectly.
  
  - I could not figure out how to get the labels at the bottom to match without having "sum of ..." preceding the label and thouhgt I was putting the data in the wrong section of the pivot table.  I thought I needed to put the percentages in the column section but that did not show up right.  When I put them in the Sum area, the table looked correct but it would not allow me to edit the names because the table already had a column named w/o "sum of ...".  In google, someone suggested adding a space to the name which worked.

---

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

- What can you conclude about the Outcomes based on Goals?

- What are some limitations of this dataset?

- What are some other possible tables and/or graphs that we could create?


