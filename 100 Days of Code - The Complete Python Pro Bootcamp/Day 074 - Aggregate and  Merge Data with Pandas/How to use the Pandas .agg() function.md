# How to use the Pandas .agg() function

Often you find yourself needing to summarise data. This is where the .groupby() function comes in really handy. However, sometimes you want to run even more operations based on a particular DataFrame column. This is where the [.agg()](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.agg.html) method comes in.

In our case, we want to calculate the number of different themes by calendar year. This means we have to group the data by year and then count the number of unique theme_ids for that year.

## Number of Themes per Calendar Year

