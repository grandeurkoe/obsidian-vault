# How to use the Pandas .agg() function

Often you find yourself needing to summarize data. This is where the `.groupby()` function comes in really handy. However, sometimes you want to run even more operations based on a particular DataFrame column. This is where the [.agg()](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.agg.html) method comes in.

In our case, we want to calculate the number of different themes by calendar year. This means we have to group the data by year and then count the number of unique `theme_ids` for that year.

## Number of Themes per Calendar Year

We can accomplish this by chaining the `.groupby()` and the `.agg()` functions together:

![[2020-10-10_10-08-17-3130eee0444d4983a649a7af0213bf17.png|500]]

Note, the `.agg()` method takes a dictionary as an argument. In this dictionary, we specify which operation we'd like to apply to each column. In our case, we just want to calculate the number of unique entries in the `theme_id` column by using our old friend, the `.nunique()` method.

Let's give our column in `themes_by_year` a more appropriate name and let's take a look at what we've got:

![[2020-10-10_10-08-30-8c14d024f59494861a599bf138da8319.png]]

Here we can see that LEGO only had 2 themes during the first few years, but just like the number of sets the number of themes expanded manifold over the years. Let's plot this on a chart again.