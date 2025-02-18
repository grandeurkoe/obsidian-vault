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
4.
5. h_bar.show()
```

We can also add a custom title and axis labels like so:

```python
1. h_bar = px.bar(x = category_installs.Installs,
2.                y = category_installs.index,
3.                orientation='h',
4.                title='Category Popularity')
5.
6. h_bar.update_layout(xaxis_title='Number of Downloads', yaxis_title='Category')
7. h_bar.show()
```


![[2020-10-11_12-51-08-abc65eebc2434504dd6457da4618a9ac.png|500]]

Now we see that Games and Tools are actually the most popular categories. If we plot the popularity of a category next to the number of apps in that category we can get an idea of how concentrated a category is. Do few apps have most of the downloads or are the downloads spread out over many apps?

## Challenge

As a challenge, let’s use Plotly to create a scatter plot that looks like this:

![[2020-10-11_12-51-37-3937d6162a4800714f6fdcbdf2b12870.png|500]]

Create a DataFrame that has the number of apps in one column and the number of installs in another:

![[2020-10-11_13-13-37-047a427b6b3dffb981c19c580f398673.png|500]]

Then use the [plotly express examples from the documentation](https://plotly.com/python/line-and-scatter/) alongside the [.scatter() API reference](https://plotly.com/python-api-reference/generated/plotly.express.scatter.html) to create scatter plot that looks like the chart above.

_Hint_: Use the `size`, `hover_name` and `color` parameters in `.scatter()`. To scale the y-axis, call `.update_layout()` and specify that the y-axis should be on a log-scale like so: `yaxis=dict(type='log')`

## Solution

First, we need to work out the number of apps in each category (similar to what we did previously).

`1. cat_number = df_apps_clean.groupby('Category').agg({'App': pd.Series.count})`

Then we can use `.merge()` and combine the two DataFrame.

```python
1. cat_merged_df = pd.merge(cat_number, category_installs, on='Category', how="inner")
2. print(f'The dimensions of the DataFrame are: {cat_merged_df.shape}')
3. cat_merged_df.sort_values('Installs', ascending=False)
```
`
Now we can create the chart. Note that we can pass in an entire DataFrame and specify which columns should be used for the x and y by column name.

```python
1. scatter = px.scatter(cat_merged_df, # data
2.                     x='App', # column name
3.                     y='Installs',
4.                     title='Category Concentration',
5.                     size='App',
6.                     hover_name=cat_merged_df.index,
7.                     color='Installs')

9. scatter.update_layout(xaxis_title="Number of Apps (Lower=More Concentrated)",
10.                       yaxis_title="Installs",
11.                       yaxis=dict(type='log'))

13. scatter.show()
```

What we see is that the categories like Family, Tools, and Game have many different apps sharing a high number of downloads. But for the categories like video players and entertainment, all the downloads are concentrated in very few apps.

![[2020-10-11_13-16-11-a310e773b06e1efc0ad4114a12a51e01.png|500]]