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
What do we see here? Well, first off we can spot Cleopatra on the far right. But also, we see that many lower budget films made much more money! The relationship between the production budget and movie revenue is not very strong. Many points on the left are very far away for the line, so the line appears not to capture the relationship between budget and revenue very well at all!

But does the same hold true for the newer films?

## Challenge

Use Seaborn's `.regplot()` to show the scatter plot and linear regression line against the `new_films`.  
  
**Style the chart**

- Put the chart on a `'darkgrid'`.
- Set limits on the axes so that they don't show negative values.
- Label the axes on the plot "Revenue in $ billions" and "Budget in $ millions".
- Provide HEX color codes for the plot and the regression line. Make the dots dark blue (#2f4b7c) and the line orange (#ff7c43).

**Interpret the chart**

- Do our data points for the new films align better or worse with the linear regression than for our older films?
- Roughly how much would a film with a budget of $150 million make according to the regression line?