![Outcomes_vs_Goals_with_Histogram](https://user-images.githubusercontent.com/60558885/110157464-32848e80-7db6-11eb-9643-acdf1766eb06.png)
# Kickstarting with Excel

## Overview of Project

### Purpose
  The purpose of this project is to perform exploratory data analysis on a set of Kickstarter campaigns. The goal is to understand how the launch date of the campaign and the goal amount of the campaign affect the outcome (successful, failure, canceled).

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date
  In order to understand the outcome of campaigns based on launch date we first created a pivot table from the original data set. Then the rows were set to be the launch date of the campaigns (by month) and the columns set to the possible campaign outcomes (excluding live campaigns). We also added the Parent Category, and Year to the filter field, and filter the data to only display theater campaigns. We then populated the table with the count of the different possible outcomes. Finally, the data was charted with launch month on the x-axis as count on the y-axis.
  
### Analysis of Outcomes Based on Goals
  To see the relationship between goal amounts and different campaign outcomes we first created a table and divided the goal amount into 12 buckets. We then used Excel's `COUNTIFS()` function to count the number of play campaigns which fell into each bucket for successful, failed, and canceled campaigns separately.We then coverted each of these raw counts to percentages by taking `COUNTIFS()/SUM()` where the sum is the total number of projects in the respective bucket. Finally we charted the percentage of successful, failed, and canceled projects across each bucket.

### Challenges and Difficulties Encountered
  We encountered few problems throughout this analysis but when using the `COUNTIFS()` function during the second part we neglected to include a condition to filter for only play campaigns which led to a different result. After discussing via slack with colleagues this issue was resolved. Other potential issues could include: forgetting to filter to the theater category in part 1, using the campaign end date instead of the launch date in part 1. Finally, it would be fairly easy to accidentally double count some of the campaigns in part 2 by using incorrect criteria in the `COUNTIFS()` function (i.e. including the end-point of one bucket and the start-point of the next bucket)

## Results

### Results of Outcomes Based On Launch Date
From the below chart and by quickly calculating the mean and standard deviation of the number of successful and failed campaigns. We can conclude that May is an exceptionally good month to start a kickstarter campaign if one wants it to succeed. While may is the peak month for both successful and failed campaigns we note that the number of successful campaigns falls outside of the interval of 2 standard deviations of the mean of successes while the number of failed campaigns falls within 2 standard deviations of the mean of failures. This can be interpreted as the peak in successes being more significant than the peak in failures. Additionally we can see that October is likely the worst month to start a kickstarter campaign since it has the second highest number of failed campaigns (50) while also having a below average number of successful campaigns. While November and December may seem worse one can note that in these months both successes and failures are below average, meaning there are fewer campaigns overall in these months

### Results of Outcomes Based on Goals
From the included chart we can see that generally smaller campaign goals translate to better odds of a successful campaign. This makes sense intuitively as well as smaller goals would require fewer backers, smaller pledges, or both. The percentage of successful campaigns is first overtaken by the percentage of failed campaigns at $15,000-$19,9999. So, in order to maximize the odds of having a successful campaign it would be better to keep the goal under $15,000, remembering that even smaller goals have better rates of success. 

### Limitations of the Dataset
One important limitation of this dataset that actually impacts the accuracy of the Outcomes Based on Goals chart is that there are very few campaigns in the plays subcategory with goals over $25,000. For example, there is only one play campaign in the 45,000. This play is a failure so the chart shows %100 failure rate for this bucket, however, if this one campaign had succeeded then we would have a %100 success rate which would almost make it seem as if some larger goals ($35,000-$49,999) had very high rates of sucess; in reality its hard to say with so few datapoints if these campaigns would be successful due to their high goal amounts or if these campaigns which had high goal amounts just happened to be the successful ones. This problem could be addressed by adding a histogram to show the distribution of data which, when placed below the Outcomes Based on Goals chart, does indeed show how few data points there are at the upper end of the axis.
