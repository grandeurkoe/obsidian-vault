# Seaborn Data Visualization: Bubble Charts

We're now ready to visualise our data. Today I want to introduce you to another popular data visualization tool that you can use alongside Plotly and Matplotlib: Seaborn. [Seaborn](https://seaborn.pydata.org/) is built on top of Matplotlib and it makes creating certain visualizations very convenient.

![[2020-10-15_09-09-20-72497b72e13443b2cebd18af668ac37e.png|500]]

## Import Seaborn

The first step is adding Seaborn to our notebook. By convention we'll use the name `sns`.

![[2020-10-15_09-10-22-4722ef6ffbcef591bc19aa7b71133683.png|500]]

## Seaborn Scatter Plots

To create a [.scatterplot()](https://seaborn.pydata.org/generated/seaborn.scatterplot.html?highlight=scatterplot#seaborn.scatterplot), all we need to do is supply our DataFrame and the column names that we'd like to see on our axes.

```python
1. sns.scatterplot(data=data_clean,
2.                 x='USD_Production_Budget', 
3.                 y='USD_Worldwide_Gross')
```

![[2020-10-15_09-13-55-0b4231f5cf7793d115a8aafa96f58d4e.png|500]]
That should look familiar. 😊 Because Seaborn is built on top of Matplotlib, we can dive into the Matplotlib layer anytime to configure our chart. For example, we can increase the size of our figure:

![[2020-10-15_09-17-22-efc609bc13bcec591aa57d00428714ad.png|500]]

And to style our chart we can simply configure the `Axes` object that is returned from `sns.scatterplot()`.

![[2020-10-15_09-19-14-d55c7a6c5b664184458469f081502617.png|500]]

Here's how:

```python
1. plt.figure(figsize=(8,4), dpi=200)
2.
3. ax = sns.scatterplot(data=data_clean,
4.                      x='USD_Production_Budget', 
5.                      y='USD_Worldwide_Gross')
6.
7. ax.set(ylim=(0, 3000000000),
8.        xlim=(0, 450000000),
9.        ylabel='Revenue in $ billions',
10.        xlabel='Budget in $100 millions')
11.
12. plt.show()
```

Here we're diving into the Matplotlib layer to set the limits on the axes and change the labels.

## From Scatter Plot to Bubble Chart

But the reason we're using Seaborn is because of the `hue` and `size` parameters that make it very easy to create a bubble chart. These parameters allow us to color the data and change their size according to one of the columns in our DataFrame.

```python
1. plt.figure(figsize=(8,4), dpi=200)
2. ax = sns.scatterplot(data=data_clean,
3.                      x='USD_Production_Budget', 
4.                      y='USD_Worldwide_Gross',
5.                      hue='USD_Worldwide_Gross', # colour
6.                      size='USD_Worldwide_Gross',) # dot size
7.
8. ax.set(ylim=(0, 3000000000),
9.        xlim=(0, 450000000),
10.        ylabel='Revenue in $ billions',
11.        xlabel='Budget in $100 millions',)
12.
13. plt.show()
```

![[2020-10-15_09-28-08-831897dbfc869643665e710decb79e5f.png|500]]

Now our higher grossing movies are bigger and darker on our chart. That's super handy. But Seaborn offers a number of convenient styling options as well.

To set the styling on a single chart (as opposed to all the charts in the entire notebook) we can use Python's `with` keyword. We've seen `with` used already when it comes to opening files in previous lessons.

```python
1. plt.figure(figsize=(8,4), dpi=200)
2.
3. # set styling on a single chart
4. with sns.axes_style('darkgrid'):
5.   ax = sns.scatterplot(data=data_clean,
6.                        x='USD_Production_Budget', 
7.                        y='USD_Worldwide_Gross',
8.                        hue='USD_Worldwide_Gross',
9.                        size='USD_Worldwide_Gross')
10.
11.   ax.set(ylim=(0, 3000000000),
12.         xlim=(0, 450000000),
13.         ylabel='Revenue in $ billions',
14.         xlabel='Budget in $100 millions')
```

![[2020-10-15_09-33-57-2840113022769b3f9be9fe8dc4667693.png|500]]

In addition to `'darkgrid'`, Seaborn has a number of [built-in themes](https://python-graph-gallery.com/104-seaborn-themes/). so you can style your chart very quickly. Try out `'whitegrid'`, `'dark'`,  or `'ticks'` for example.

## Challenge

Now that you've seen how to create a beautiful bubble chart in Seaborn, it's time to create your own. Can you write the code to replicate this chart? Notice how we are actually representing THREE dimensions in this chart: the budget, the release date, and the worldwide revenue. This is what makes bubble charts so awesomely informative.

![[2020-10-15_09-44-00-eac16a0a1c99356a123eb410d99157ec.png|500]]

## Solution: Movie Budgets over Time

Alright, I hope that was fairly straightforward. All you needed to do is change a few arguments:

```python
1. plt.figure(figsize=(8,4), dpi=200)
2.
3. with sns.axes_style("darkgrid"):
4.     ax = sns.scatterplot(data=data_clean, 
5.                     x='Release_Date', 
6.                     y='USD_Production_Budget',
7.                     hue='USD_Worldwide_Gross',
8.                     size='USD_Worldwide_Gross',)
9.
10.     ax.set(ylim=(0, 450000000),
11.            xlim=(data_clean.Release_Date.min(), data_clean.Release_Date.max()),
12.            xlabel='Year',
13.            ylabel='Budget in $100 millions')
```

## Analysis

What do we see here? What is this chart telling us? Well, first off, movie budgets have just exploded in the last 40 years or so. Up until the 1970s, the film industry appears to have been in an entirely different era. Budgets started growing fast from the 1980s onwards and continued to grow through the 2000s. Also, the industry has grown massively, producing many more films than before. The number of data points is so dense from 2000 onwards that they are overlapping.

![[2020-10-15_10-00-28-26cc75fe26fee70f2445c638aa490791.png|500]]