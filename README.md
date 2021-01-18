# School_District_Analysis

## Overview

The purpose of this analysis was to examine the data collected from multiple schools within a district to determine the trends that exist among them. The original data collected then had to be altered and reexamined due to the existence of academic dishonesty that made a portion of the data unreliable.

## Results

As seen in the image below, the original data indicated the district had:

![Unreliable Data Not Removed](/Resources/districtSummary.png)

- 15 total schools
- 39,170 total students
- A budget of $24,649,428.00
- An average Math score of 79.0%
- An average Reading score of 81.9%
- 75% of students passing Math
- 86% of students passing Reading
- 65% of students passing both Math and Reading

However, once the data was affected data was removed from the analysis we saw changes to some of categories:

![Unreliable Data Removed](/Resources/districtSummaryNew.png)

- The average Math score decreased to 78.9%
- The percentage of students passing Math lowered to 74.8%
- The percentage of students passing Reading lowered to 85.7%
- The percentage of students passing both Math and Reading decreased to 64.9%
- There was no change in the average Reading score, the total budget, the total number of students, nor the total number of schools in the district

Because the data affected by the academic dishonesty was only related to Thomas High School, we can see it was the only school that saw a change in their performance data in the `per_school_summary_df`.

![Unreliable Data Not Removed](/Resources/perSchoolSummary.png)

![Unreliable Data Removed](/Resources/perSchoolSummaryAdjusted.png)

We can see that while the general performance of Thomas High School did drop due to the removal of the unreliable data, it was not a significant enough drop to move it out of the second best performing school.
By entering the code `top_schools.head()` we can see the ranking of the top 5 schools have remained unchanged, despite a drop in the % Overall Passing Series

![Unreliable Data Not Removed](/Resources/topSchools.png)

![Unreliable Data Removed](/Resources/topSchoolsNew.png)

The only grade averages that were affected by the removal of the unreliable data was the 9th grade, and again only Thomas High School was affected. Because the entire grade's scores were removed they were replaced by `nan` in the `math_scores_by_grade` and `reading_scores_by_grade` DataFrames.

The following analyses were not affected by the removal of the unreliable data:

- Scores by school spending
- Scores by school size
- Scores by school type

## Summary

Upon the removal of the unreliable data, we saw several major changes to the data. The scores that were affected appeared to have caused the averages for Math in the district to decrease. While only a small amount, it was enough to cause the original analysis of Math in the district unreliable. We also saw a decrease in the every % Passing category (% Passing Math, % Passing Reading, and % Overall passing). This is likely because Thomas High School is a high performing school, and by removing the data from that school, the entire district suffered in performance. As we can see from the `top_schools.head()` DataFrame, even after removing the offending data, Thomas High School remained the second highest performing schools based on their averages for grades 11th-12th.