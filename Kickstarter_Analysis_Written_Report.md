# Kickstarting with Excel

## Overview of Project

### Purpose
This project aims to help Louise, a playwright, to have a better understanding of her crowdfunding campaign. Through this report Louise could figure out the different campaigns performance relation to their launch dates and their funding goals. And she would mirror those conclusions to future other successful campaigns.  
## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date

### Analysis of Outcomes Based on Goals

### Challenges and Difficulties Encountered

#### Difficulty 1
- Difficulty: When create the pivot table instead of selecting any cell in Kickstarter worksheet, I select the whole worksheet. Therefore, a (blank) display in both row and column (Figure 1), driving me frustrated. It is the first time I see this issue and could not recall the additional step I had done comparing with previous practice. 
- Solution: Firstly, I googled why there was a blank in a pivot table. Unfortunately, the most related results were only focus on how to delete the blank did not explain the reason why it showed up. Then I decided to try delete it first and waited to ask the root cause during the office hour. During the delete process, an idea entered my thoughts in a split second that I might select some blank cells when created the pivot table, why not just taking a second chance to insert a new pivot table without any blank cells. It turns out I am on the right track, this time there is no more blank in my new pivot table.

#### Difficulty 2
- Difficulty: At the time using COUNTIFS(), I did a double check on the grand total of each successful results comparing with the number directly retrieve from =COUNTIFS(Kickstarter!$F:$F,"successful",Kickstarter!$R:$R,"plays"). An obvious difference popped up and reminded me there must be some missing data I should add.
- Solution: I went through the dollar-amount range of the “Goal” to understand the logic of each group and realized that I need to add “equal to” in each formula expect the Less Than 1,000. Since each group dose not have any overlaps, I should include the start and end number. Therefore, I modified my formula from =COUNTIFS(Kickstarter!$F:$F,"successful",Kickstarter!$R:$R,"plays",Kickstarter!$D:$D,">1000",Kickstarter!$D:$D,"<4999") to =COUNTIFS(Kickstarter!$F:$F,"successful",Kickstarter!$R:$R,"plays",Kickstarter!$D:$D,">=1000",Kickstarter!$D:$D,"<=4999"), the problem is successfully solved. 


## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

- What can you conclude about the Outcomes based on Goals?

- What are some limitations of this dataset?

- What are some other possible tables and/or graphs that we could create?
