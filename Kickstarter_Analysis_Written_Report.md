# Kickstarting with Excel

## Overview of Project

### Purpose
This project aims to help Louise, a playwright, to have a better understanding of her crowdfunding campaign. With the finding Louise could figure out the different campaigns performance relation to their launch dates and their funding goals. It may work as reference for the other ones in the same category.  
## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date

The pivot table is an efficient approach to analyze the relationship between campaign outcomes and their launch date. To make the analysis more reliable, we narrow down the parent category to only one, theater.  And with a line chart we could better understand the analysis outcomes. We could get the following result. 
![image](https://github.com/Jarviniazh/Module-1-Challenge-Kickstarter-Analysis/blob/main/Resources/Theater_Outcomes_vs_Launch.png)

  1.	There is 1,369 activities Louise held during the crowdfunding under theater category. And over half of the outcomes are successful, followed by 493 failed cases and 37 canceled one. That means most of activities could raise the amount set by the goals. And only a few were terminated before the deadline. 
  2.	The line of successful cases, with the highest amount at 111, and the lowest at 37, is more fluctuant than the other two. However, for canceled one it shows a most flat line throughout the whole year. 
  3.	There seems a time trend on both successful and failed outcomes throughout the nine-year campaign. Numbers increase from January to February, then back to almost the same number as January in March. From March to May the outcomes gradually grow until reaching the highest point in May. Later the campaign under theater category experiences a consistent drop until September. 
  4.	After a marginally rebound in October, the trend of successful outcomes differs from the failed one. The former keeps falling to its lowest level in December, while the later tends to be more fluctuant. 

### Analysis of Outcomes Based on Goals

Besides the launch date, a proper number set to a goal may also impact the success rate of a campaign. In this part we narrow down the target group even further to a subcategory under theater – plays. First, from less than $1,000 to greater than $50,000 we divide the goal to 10 ranges every $5,000, one less than $1,000 and one greater than $50,000, in total 12 ranges. Then we count all numbers of successful, failed, and canceled activities within each range. Afterwards, it is easy to calculate the rate of successful, failed and canceled separately. The graph below shows the analysis results we get. 
![image](https://github.com/Jarviniazh/Module-1-Challenge-Kickstarter-Analysis/blob/main/Resources/Outcomes_vs_Goals.png)

  1.	Happily, there is none of canceled case among the plays subcategory. And both successful rates and failed rates are quite fluctuant among the 12 ranges. 
  2.	Successful rates and failed rates share a negative relationship. The successful rates have a peak about 76% when the goal is less than $1,000, then shows a downward trend from following range until 25,00 to $29,999. This line rises rapidly to a constant rate about 67%, which the fundraising goal is less than and equal to $44,999, before dramatically decrease to reach the lowest level of 0 percent between $45,000 to $49,999. In other words, the campaign completely failed with this range. 
  3.	At the point the goal amount is among $15,000 to $19,999, successful rate is equal to failed rate. After that the failed rate exceed the successful rate.
  4.	Within $5,000 to $24,999 range, the differences between successful rate and failed rate are less than or equal to 10 percent, the smallest gap in this chart.


### Challenges and Difficulties Encountered

#### Difficulty 1
- Difficulty: When create the pivot table instead of selecting any cell in Kickstarter worksheet, I select the whole worksheet. Therefore, a (blank) display in both row and column, driving me frustrated. It is the first time I see this issue and could not recall the additional step I had done comparing with previous practice. 
   ![Image](https://github.com/Jarviniazh/Module-1-Challenge-Kickstarter-Analysis/blob/main/Resources/Difficulty1.png)
- Solution: Firstly, I googled why there was a blank in a pivot table. Unfortunately, the most related results were only focus on how to delete the blank did not explain the reason why it showed up. Then I decided to try delete it first and waited to ask the root cause during the office hour. During the delete process, an idea entered my thoughts in a split second that I might select some blank cells when created the pivot table, why not just taking a second chance to insert a new pivot table without any blank cells. It turns out I am on the right track, this time there is no more blank in my new pivot table.

#### Difficulty 2
- Difficulty: At the time using COUNTIFS(), I did a double check on the grand total of each successful results comparing with the number directly retrieve from =COUNTIFS(Kickstarter!$F:$F,"successful",Kickstarter!$R:$R,"plays"). An obvious difference popped up and reminded me there must be some missing data I should add.
  ![Image](https://github.com/Jarviniazh/Module-1-Challenge-Kickstarter-Analysis/blob/main/Resources/Difficulty2.png)
- Solution: I went through the dollar-amount range of the “Goal” to understand the logic of each group and realized that I need to add “equal to” in each formula expect the Less Than 1,000. Since each group dose not have any overlaps, I should include the start and end number. Therefore, I modified my formula from =COUNTIFS(Kickstarter!$F:$F,"successful",Kickstarter!$R:$R,"plays",Kickstarter!$D:$D,">1000",Kickstarter!$D:$D,"<4999") to =COUNTIFS(Kickstarter!$F:$F,"successful",Kickstarter!$R:$R,"plays",Kickstarter!$D:$D,">=1000",Kickstarter!$D:$D,"<=4999"), the problem is successfully solved. 


## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?
  1. Overall the successful cases are way more than the failed and the canceled ones. And the canceled ones are relatively low that she might not consider seriously during the campaign.
  2. Summertime (May to September) seems to be a proper campaign season for Louise. During those months she could obtain the greatest number of feedbacks. And the other months the outcomes might fluctuant.

- What can you conclude about the Outcomes based on Goals?
  - To guarantee a higher successful rate of her fundraising campaign, we suggest Louise set her goal no greater than $19,999, the higher goal will lead to a greater change of failure. Though the lower the mount, the higher successful rate she would obtain, considering the efficiency and her budget, it is better to have a goal no less than $1,000.

- What are some limitations of this dataset?
  1. The dataset was collected between 2009 to 2017, might not reflect the current circumstances, since the inflation rate rises a lot and people may change their entertainment preferences.
  2. The dataset contains multiple countries outcomes. Therefore, it is hard to set a general goal of funding goals, due to the different income level and denomination of currency. 
  3. The different currencies would impact the analysis of the relation between outcomes and their funding goals and decrease the reliability of our conclusion. It is better to set a benchmark currency, then convert the other to that benchmark currency

- What are some other possible tables and/or graphs that we could create?
  1. Bar chart: easy to compare the data between different outcomes at a glance. Besides understand the trend differences using line chart, we could use bar chart to shows which month or goal range would lead to the highest number of successful.
  2. Box and Whisker: this graph could help us figure out whether there are any outliers in the dataset, then adjust some analysis approach based on the results.
