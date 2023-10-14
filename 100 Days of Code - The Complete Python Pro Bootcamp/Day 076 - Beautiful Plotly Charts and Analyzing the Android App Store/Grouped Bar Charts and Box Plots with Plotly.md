# Grouped Bar Charts and Box Plots with Plotly

Now that we’ve looked at the total number of apps per category and the total number of apps per genre, let’s see what the split is between free and paid apps.

`1. df_apps_clean.Type.value_counts()`

We see that the majority of apps are free on the Google Play Store. But perhaps some categories have more paid apps than others. Let’s investigate. We can group our data first by Category and then by Type. Then we can add up the number of apps per each type. Using `as_index=False` we push all the data into columns rather than end up with our Categories as the index.

```python
1. df_free_vs_paid = df_apps_clean.groupby(["Category", "Type"], as_index=False).agg({'App': pd.Series.count}).sort_values('App')
2. df_free_vs_paid.head()
```

![[2020-10-11_13-46-00-2dc5178caf548bb86a9ad238e7dc671a.png|500]]

Unsurprisingly the biggest categories have the most paid apps. However, there might be some patterns if we put the numbers of a graph!

## Challenge

Use the Plotly express bar [chart examples](https://plotly.com/python/bar-charts/#bar-chart-with-sorted-or-ordered-categories) and the [.bar() API reference](https://plotly.com/python-api-reference/generated/plotly.express.bar.html#plotly.express.bar) to create this bar chart:

![[2020-10-11_13-46-44-c19715fca6ba4ca0dcaedfccb9725f83.png|500]]

You'll want to use the `df_free_vs_paid` DataFrame that you created above that has the total number of free and paid apps per category.

See if you can figure out how to get the look above by changing the `categoryorder` to `'total descending'` as outlined in the documentation [here](https://plotly.com/python/categorical-axes/#automatically-sorting-categories-by-name-or-total-value).

## Solution

### Contrasting Free vs. Paid Apps per Category

The key is using the `color` and `barmode` parameters for the `.bar()` method. To get a particular order, you can pass a dictionary to the axis parameter in `.update_layout()`.

```python
1. g_bar = px.bar(df_free_vs_paid,
2.                x='Category',
3.                y='App',
4.                title='Free vs Paid Apps by Category',
5.                color='Type',
6.                barmode='group')

8. g_bar.update_layout(xaxis_title='Category',
9.                     yaxis_title='Number of Apps',
10.                     xaxis={'categoryorder':'total descending'},
11.                     yaxis=dict(type='log'))

13. g_bar.show()
```
