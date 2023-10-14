# Plotly Bar Charts & Scatter Plots: The Most Competitive & Popular App Categories

If you were to release an app, would you choose to go after a competitive category with many other apps? Or would you target a popular category with a high number of downloads? Or perhaps you can target a category which is both popular but also one where the downloads are spread out among many different apps. That way, even if it’s more difficult to discover among all the other apps, your app has a better chance of getting installed, right? Let’s analyze this with bar charts and scatter plots and figure out which categories are dominating the market.

We can find the number of different categories like so:

`1. df_apps_clean.Category.nunique()`

Which shows us that we there are 33 unique categories.

To calculate the number of apps per category we can use our old friend `.value_counts()`

`1. top10_category = df_apps_clean.Category.value_counts()[:10]`

![[2020-10-11_12-50-03-484dad1e2ae6699a90c68800f1a24ca9.png|500]]

To visualise this data in a bar chart we can use the Plotly express (our px) [bar()](https://plotly.com/python-api-reference/generated/plotly.express.bar.html#plotly.express.bar) function:

```python
1. bar = px.bar(x = top10_category.index, # index = category name
2.              y = top10_category.values)
3.
4. bar.show()
```

![[2020-10-11_12-50-27-18f0bf39f584e83d11de5a269b080336.png|500]]

But what if we look at it from a different perspective? What matters is not just the total number of apps in the category but how often apps are downloaded in that category. This will give us an idea of how popular a category is. First, we have to group all our apps by category and sum the number of installations:

```python
1. category_installs = df_apps_clean.groupby('Category').agg({'Installs': pd.Series.sum})
2. category_installs.sort_values('Installs', ascending=True, inplace=True)
```

Then we can create a horizontal bar chart, simply by adding the orientation parameter:

```python
1. h_bar = px.bar(x = category_installs.Installs,
2.                y = category_installs.index,
3.                orientation='h')

5. h_bar.show()

We can also add a custom title and axis labels like so:

1. h_bar = px.bar(x = category_installs.Installs,
2.                y = category_installs.index,
3.                orientation='h',
4.                title='Category Popularity')

6. h_bar.update_layout(xaxis_title='Number of Downloads', yaxis_title='Category')
7. h_bar.show()
```
