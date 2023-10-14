# Data Visualization with Plotly: Create Pie and Donut Charts

All Android apps have a content rating like “Everyone” or “Teen” or “Mature 17+”. Let’s take a look at the distribution of the content ratings in our dataset and see how to visualise it with [plotly](https://plotly.com/python/) - a popular data visualisation library that you can use alongside or instead of Matplotlib.

First, we’ll count the number of occurrences of each rating with `.value_counts()`

`1. ratings = df_apps_clean.Content_Rating.value_counts()`

![[2020-10-10_11-59-55-d92168b181149464c7edad65547e7859.png|500]]

The first step in creating charts with Plotly is to `import` `plotly.express`. This is the fastest way to create a beautiful graphic with a minimal amount of code in Plotly.

![[2020-10-10_12-00-08-bbf5ed815dadf9c64cf82f064bdd7ad2.png|500]]

