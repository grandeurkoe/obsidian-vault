# The Effect of Handwashing

In June 1846, Dr. Semmelweis ordered everyone on his medical staff to start cleaning their hands and instruments not just with soap and water but with a chlorine solution (he didn't know it at the time, but chlorine is an amazing disinfectant). The reason Dr. Semmelweis actually chose the chlorine was that he wanted to get rid of any smell on doctors' hands after an autopsy. No one knew anything about bacteria, germs or viruses at the time.

## Challenge 1: The Effect of Handwashing

- Add a column called "`pct_deaths`" to `df_monthly` that has the percentage of deaths per birth for each row.
- Create two subsets from the `df_monthly` data: before and after Dr. Semmelweis ordered washing hand.
- Calculate the average death rate prior to June 1847.
- Calculate the average death rate after June 1847.

## Challenge 2: Calculate a Rolling Average of the Death Rate

Create a DataFrame that has the 6-month rolling average death rate prior to mandatory handwashing.

_Hint_: You'll need to set the dates as the index in order to avoid the date column being dropped during the calculation

## Challenge 3: Highlighting Subsections of a Line Chart

Copy-paste and then modify the Matplotlib chart from before to plot the monthly death rates (instead of the total number of births and deaths). The chart should look something like this:

![[2020-10-23_12-27-28-063144e4acbc37b96bfd66f6f25f75f3.png|500]]

- Add 3 separate lines to the plot: the death rate before handwashing, after handwashing, and the 6-month moving average before handwashing.
- Show the monthly death rate before handwashing as a thin dashed black line.
- Show the moving average as a thicker, crimson line.
- Show the rate after handwashing as a `skyblue` line with round markers.
- Look at the [code snippet in the documentation to see how you can add a legend](https://matplotlib.org/3.1.1/api/_as_gen/matplotlib.pyplot.legend.html) to the chart.

## Solution to Challenge 1

We can add a column with the proportion of deaths per birth like so:

`1. df_monthly['pct_deaths'] = df_monthly.deaths/df_monthly.births`

Then we can create two subsets based on the `handwashing_start` date.

```python
1. before_washing = df_monthly[df_monthly.date < handwashing_start]
2. after_washing = df_monthly[df_monthly.date >= handwashing_start]
```

The death rate per birth dropped dramatically after handwashing started - from close to 10.53% to 2.15%. We can use the colon and dot inside a print statement to determine the number of digits we'd like to print out from a number.

```python
1. bw_rate = before_washing.deaths.sum() / before_washing.births.sum() * 100
2. aw_rate = after_washing.deaths.sum() / after_washing.births.sum() * 100
3. print(f'Average death rate before 1847 was {bw_rate:.4}%')
4. print(f'Average death rate AFTER 1847 was {aw_rate:.3}%')
```