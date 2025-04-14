# Data Visualization with Plotly: Create Pie and Donut Charts

All Android apps have a content rating like “Everyone” or “Teen” or “Mature 17+”. Let’s take a look at the distribution of the content ratings in our dataset and see how to visualise it with [plotly](https://plotly.com/python/) - a popular data visualisation library that you can use alongside or instead of Matplotlib.

First, we’ll count the number of occurrences of each rating with `.value_counts()`

`1. ratings = df_apps_clean.Content_Rating.value_counts()`

![[2020-10-10_11-59-55-d92168b181149464c7edad65547e7859.png|500]]

The first step in creating charts with Plotly is to `import` `plotly.express`. This is the fastest way to create a beautiful graphic with a minimal amount of code in Plotly.

![[2020-10-10_12-00-08-bbf5ed815dadf9c64cf82f064bdd7ad2.png|500]]

To create a pie chart we simply call `px.pie()` and then `.show()` the resulting figure. Plotly refers to all their figures, be they line charts, bar charts, or pie charts as `graph_objects`.

![[2020-10-10_12-00-31-31b7402c83df9ab64a30eca64147d286.png|500]]

Let’s customize our pie chart. Looking at the [.pie() documentation](https://plotly.com/python-api-reference/generated/plotly.express.pie.html) we see a number of parameters that we can set, like title or names.

![[2020-10-10_12-00-52-8e188db47a2c59e78c59597ac9f58130.png|500]]

If you’d like to configure other aspects of the chart, that you can’t see in the list of parameters, you can call a method called `.update_traces()`. In Plotly lingo, “traces” refer to graphical marks on a figure. Think of “traces” as collections of attributes. Here we update the traces to change how the text is displayed.

```python
1. fig = px.pie(labels=ratings.index,
2. values=ratings.values,
3. title="Content Rating",
4. names=ratings.index,
5. )
6. fig.update_traces(textposition='outside', textinfo='percent+label')

8. fig.show()
```

![[2020-10-10_12-01-14-05cf469b8bad01ae65343706f70f3feb.png|500]]

To create a donut 🍩 chart, we can simply add a value for the `hole` argument:

```python
1. fig = px.pie(labels=ratings.index,
2. values=ratings.values,
3. title="Content Rating",
4. names=ratings.index,
5. hole=0.6,
6. )
7. fig.update_traces(textposition='inside', textfont_size=15, textinfo='percent')

9. fig.show()
```

![[2020-10-10_12-01-52-9743066db238bd044fd095783c3261e1.png|500]]