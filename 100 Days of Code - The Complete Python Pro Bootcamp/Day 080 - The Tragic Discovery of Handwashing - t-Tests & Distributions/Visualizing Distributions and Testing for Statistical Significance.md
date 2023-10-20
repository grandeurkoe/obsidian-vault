# Visualizing Distributions and Testing for Statistical Significance

There are even more powerful arguments we can make to convince our fellow doctors in clinic 1 of the virtues of handwashing. The first are statistics regarding the mean monthly death rate. The second are compelling visualizations to accompany the statistics.

## Challenge 1: Calculate the Difference in the Average Monthly Death Rate

- What was the average percentage of monthly deaths before handwashing (i.e., before June 1847)?
- What was the average percentage of monthly deaths after handwashing was made obligatory?
- By how much did handwashing reduce the average chance of dying in childbirth in percentage terms?
- How do these numbers compare to the average for all the 1840s that we calculated earlier?
- How many times lower are the chances of dying after handwashing compared to before?

## Solution to Challenge 1

A lot of statistical tests rely on comparing features of distributions, like the mean. We see that the average death rate before handwashing was 10.5%. After handwashing was made obligatory, the average death rate was 2.11%. The difference is massive. Handwashing decreased the average death rate by 8.4%, a 5x improvement. 😮

```python
1. avg_prob_before = before_washing.pct_deaths.mean() * 100
2. print(f'Chance of death during childbirth before handwashing: {avg_prob_before:.3}%.')
3.
4. avg_prob_after = after_washing.pct_deaths.mean() * 100
5. print(f'Chance of death during childbirth AFTER handwashing: {avg_prob_after:.3}%.')
6.
7. mean_diff = avg_prob_before - avg_prob_after
8. print(f'Handwashing reduced the monthly proportion of deaths by {mean_diff:.3}%!')
9.
10. times = avg_prob_before / avg_prob_after
11. print(f'This is a {times:.2}x improvement!')
```

## Challenge 2: Using Box Plots to Show How the Death Rate Changed Before and After Handwashing

The statistic above is impressive, but how do we show it graphically? With a box plot we can show how the quartiles, minimum, and maximum values changed in addition to the mean.

- Use [NumPy's `.where()` function](https://numpy.org/doc/stable/reference/generated/numpy.where.html) to add a column to `df_monthly` that shows if a particular date was before or after the start of handwashing.
- Then use Plotly to create box plot of the data before and after handwashing.
- How did key statistics like the mean, max, min, 1st and 3rd quartile changed as a result of the new policy