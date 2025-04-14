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

## Challenge

Create a line plot of the number of themes released year-on-year. Only include the full calendar years in the dataset (1949 to 2019).

## Solution

  

`1. plt.plot(themes_by_year.index[:-2], themes_by_year.nr_themes[:-2])`

Again, we're using the same slicing technique as before. In the chart, we can see that LEGO has pretty consistently added more and more themes until the mid-1990s. From then the number of themes has stagnated for around 10 years or so until the early 2010s.

![[2020-10-10_10-08-56-931b5f190a914aae2db436a019b694c3.png|500]]