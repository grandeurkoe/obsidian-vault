# Data Visualization with Matplotlib

## Matplotlib

To create our first charts we're going to use a library called [Matplotlib](https://matplotlib.org/). There are many different libraries in Python to help us create charts and graphs. Matplotlib is an incredibly popular one and it works beautifully in combination with Pandas, so let's check it out.

First, we have to import Matplotlib.

`import matplotlib.pyplot as plt`

Let's do this at the top:

![[2020-09-23_14-56-02-24faa2ac03cb6eb41b5f7135d3ad16bb.png|500]]

Supply the values for the horizontal axis (the x-values) and the vertical axis (the y-values) for the chart. The x-values are our dates and the y-values are the number of posts. We can supply these values to the .plot() function by position like so:

`plt.plot(reshaped_df.index, reshaped_df.java)`

or like so if you prefer the square bracket notation.

`plt.plot(reshaped_df.index, reshaped_df['java'])`

## Styling the Chart

Let's look at a couple of methods that will help us style our chart:

`.figure()` - allows us to resize our chart

`.xticks()` - configures our x-axis

`.yticks()` - configures our y-axis

`.xlabel()` - add text to the x-axis

`.ylabel()` - add text to the y-axis

`.ylim()` - allows us to set a lower and upper bound

To make our chart larger we can provide a width (16) and a height (10) as the `figsize` of the figure.

```python
plt.figure(figsize=(16,10)) 
plt.plot(reshaped_df.index, reshaped_df.java)
```

This will make our chart easier to see. But when we increase the size of the chart, we should also increase the fontsize of the ticks on our axes so that they remain easy to read:

![[2020-09-23_15-22-03-5e3878721c6ef654b50130ee8825c22e.png|500]]

Now we can add labels. Also, we're never going to get less than 0 posts, so let's set a lower limit of 0 for the y-axis with `.ylim()`.

```python
plt.xlabel('Date', fontsize=14)
plt.ylabel('Number of Posts', fontsize=14)
plt.ylim(0, 35000)
```

![[2020-09-23_15-26-17-522ea65f0dbcd7a8f2d59028698b2cdc.png|500]]