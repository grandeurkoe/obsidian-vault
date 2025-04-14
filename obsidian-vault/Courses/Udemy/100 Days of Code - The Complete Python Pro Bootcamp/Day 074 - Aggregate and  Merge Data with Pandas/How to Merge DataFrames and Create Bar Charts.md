# How to Merge DataFrame and Create Bar Charts

Wouldn't it be nice if we could combine our data on theme names with the number sets per theme? 

Let's use the [.merge() method](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.merge.html?highlight=merge#pandas.DataFrame.merge) to combine two separate DataFrames into one. The merge method works on columns with the same **name** in both DataFrames.

Currently, our theme_ids and our number of sets per theme live inside a Series called `set_theme_count`.

![[2020-10-10_10-22-32-26ca451e68832f127ca7c6cb4608af04.png|500]]

![[2020-10-10_10-22-32-26ca451e68832f127ca7c6cb4608af04 1.png|500]]

To make sure we have a column with the name `id`, I'll convert this Pandas Series into a Pandas DataFrame.

![[2020-10-10_10-22-41-1a15ad7b2cb2c0fc80fdd8755ae68fef.png|500]]

Here I'm providing a dictionary to create the DataFrame. The keys in the dictionary become my column names.

## The Pandas .merge() function

To [.merge()](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.merge.html) two DataFrame along a particular column, we need to provide our two DataFrames and then the **column name** on which to merge. This is why we set `on='id'`. Both our `set_theme_count` and our `themes` DataFrame have a column with this name.

```python
1. merged_df = pd.merge(set_theme_count, themes, on='id')
```

The first 3 rows in our merged DataFrame look like this:

![[2020-10-10_10-23-08-5d894473bb671b773bffa7dea43bd6e1.png|500]]

Aha! Star Wars is indeed the theme with the most LEGO sets. Let's plot the top 10 themes on a chart.

## Creating a Bar Chart

Matplotlib can create almost any chart imaginable with very few lines of code. Using [.bar()](https://matplotlib.org/3.3.2/api/_as_gen/matplotlib.pyplot.bar.html) we can provide our theme names and the number of sets. This is what we get:

![[2020-10-10_10-23-26-ffad46550f606a5df52fc267b1aba0f4.png|500]]

That worked, but it's almost unreadable. 😩 The good thing for us is that we already know how to customize our charts! Here's what we get when we increase the size of our figure, add some labels, and most importantly, rotate the category names on the x-axis so that they don't overlap.

```python
1. plt.figure(figsize=(14,8))
2. plt.xticks(fontsize=14, rotation=45)
3. plt.yticks(fontsize=14)
4. plt.ylabel('Nr of Sets', fontsize=14)
5. plt.xlabel('Theme Name', fontsize=14)

7. plt.bar(merged_df.name[:10], merged_df.set_count[:10])
```

![[2020-10-10_10-23-53-a3f1d8fb51bca0e045b9ed97d58b787a.png|500]]