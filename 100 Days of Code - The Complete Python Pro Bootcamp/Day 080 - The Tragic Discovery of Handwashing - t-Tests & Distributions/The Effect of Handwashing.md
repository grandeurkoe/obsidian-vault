# The Effect of Handwashing

In June 1846, Dr. Semmelweis ordered everyone on his medical staff to start cleaning their hands and instruments not just with soap and water but with a chlorine solution (he didn't know it at the time, but chlorine is an amazing disinfectant). The reason Dr. Semmelweis actually chose the chlorine was that he wanted to get rid of any smell on doctors' hands after an autopsy. No one knew anything about bacteria, germs or viruses at the time.

## Challenge 1: The Effect of Handwashing

- Add a column called "`pct_deaths`" to `df_monthly` that has the percentage of deaths per birth for each row.
- Create two subsets from the `df_monthly` data: before and after Dr. Semmelweis ordered washing hand.
- Calculate the average death rate prior to June 1846.
- Calculate the average death rate after June 1846.

## Challenge 2: Calculate a Rolling Average of the Death Rate

Create a DataFrame that has the 6-month rolling average death rate prior to mandatory handwashing.

_Hint_: You'll need to set the dates as the index in order to avoid the date column being dropped during the calculation

## Challenge 3: Highlighting Subsections of a Line Chart

Copy-paste and then modify the Matplotlib chart from before to plot the monthly death rates (instead of the total number of births and deaths). The chart should look something like this: