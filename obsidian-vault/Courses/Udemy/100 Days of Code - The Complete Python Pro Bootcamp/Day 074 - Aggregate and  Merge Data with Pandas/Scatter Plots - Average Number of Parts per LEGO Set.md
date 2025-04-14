# Scatter Plots: Average Number of Parts per LEGO Set

## Complexity Over Time

Have LEGO sets become larger and more complex over time? Let's work out the average number of parts per LEGO set. This is the perfect time to revise how to use the `.agg()` function.

Create a Pandas Series called `parts_per_set` that has the year as the index and contains the average number of parts per LEGO set in that year. Here's what you're looking to create:

![[2020-10-10_10-11-58-4e895c1ac91304e77d46237783c84c9b.png|200]]

Once again, we're going to use the `.groupby()` and the `.agg()` function together to work this one out. However, this time we pass a dictionary to the `.agg()` function so that we will target the `num_parts` column with the `mean()` function. That way, we group our data by year and then we average the number of parts for that year.

```python
1. parts_per_set = sets.groupby('year').agg({'num_parts': pd.Series.mean})
```


To visualize our `parts_per_set` data, let's create a scatter plot. A scatter plot simply uses dots to represent the values of each data point.

You can use [the Matplotlib documentation](https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.scatter.html) to generate the scatter plot chart. Do you spot a trend in the chart? Again, you'll have to exclude the last two observations.

## Create a Scatter Plot

We just need to call the `.scatter()` instead of the `.plot()` method to create the chart. For the x-values, we'll use the index of the `parts_per_set` Series (the years) and for the y-values, we'll use the values of the series (the column name happens to be `num_parts`).

![[2020-10-10_10-15-47-b8bc9bc843254bc8e27d2f36adee1560.png|500]]

From the chart, we can definitely make out an upward trend in the size and complexity of the LEGO sets based on the average number of parts. In the 2010s the average set contained around 200 individual pieces, which is roughly double what average LEGO set used to contain in the 1960s.