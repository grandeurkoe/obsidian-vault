# Grouped Bar Charts and Box Plots with Plotly

Now that we’ve looked at the total number of apps per category and the total number of apps per genre, let’s see what the split is between free and paid apps.

`1. df_apps_clean.Type.value_counts()`

We see that the majority of apps are free on the Google Play Store. But perhaps some categories have more paid apps than others. Let’s investigate. We can group our data first by Category and then by Type. Then we can add up the number of apps per each type. Using `as_index=False` we push all the data into columns rather than end up with our Categories as the index.

```python
1. df_free_vs_paid = df_apps_clean.groupby(["Category", "Type"], as_index=False).agg({'App': pd.Series.count})
2. df_free_vs_paid.head()
```

