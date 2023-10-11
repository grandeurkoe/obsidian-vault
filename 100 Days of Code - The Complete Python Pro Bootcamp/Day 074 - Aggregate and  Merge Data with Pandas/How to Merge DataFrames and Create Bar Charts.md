# How to Merge DataFrame and Create Bar Charts

Wouldn't it be nice if we could combine our data on theme names with the number sets per theme? 

Let's use the [.merge() method](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.merge.html?highlight=merge#pandas.DataFrame.merge) to combine two separate DataFrames into one. The merge method works on columns with the same **name** in both DataFrames.

Currently, our theme_ids and our number of sets per theme live inside a Series called `set_theme_count`.

![[2020-10-10_10-22-32-26ca451e68832f127ca7c6cb4608af04.png|500]]

