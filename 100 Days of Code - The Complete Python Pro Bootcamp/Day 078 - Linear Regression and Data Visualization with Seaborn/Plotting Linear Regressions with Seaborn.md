# Plotting Linear Regressions with Seaborn

Let's visualise the relationship between the movie budget and the worldwide revenue using linear regression. Seaborn makes this incredibly easy with the [.regplot()](https://seaborn.pydata.org/generated/seaborn.regplot.html#seaborn.regplot) function.

Let's visualise the relationship between the movie budget and the worldwide revenue using linear regression. Seaborn makes this incredibly easy with the [.regplot()](https://seaborn.pydata.org/generated/seaborn.regplot.html#seaborn.regplot) function.

```python
1. sns.regplot(data=old_films, 
2.             x='USD_Production_Budget',
3.             y='USD_Worldwide_Gross')
```

This creates a scatter plot and draws a linear regression line together with the confidence interval at the same time.

To style the chart further, we can once again, drop into the Matplotlib layer and supply keyword arguments as dictionaries. We can customize the scatter plot (e.g., by changing the transparency of the dots) and the regression line itself (e.g., by changing the color).

```python
1. plt.figure(figsize=(8,4), dpi=200)
2. with sns.axes_style("whitegrid"):
3.   sns.regplot(data=old_films, 
4.             x='USD_Production_Budget', 
5.             y='USD_Worldwide_Gross',
6.             scatter_kws = {'alpha': 0.4},
7.             line_kws = {'color': 'black'})
```

![[2020-10-16_11-54-26-bf6d69797f23a0d34875a64c59e36720.png|500]]
