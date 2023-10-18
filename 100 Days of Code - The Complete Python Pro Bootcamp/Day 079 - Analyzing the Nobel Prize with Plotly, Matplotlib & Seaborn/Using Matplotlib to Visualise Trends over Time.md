# Using Matplotlib to Visualise Trends over Time

Now let's look at how things have changed over time. This will give us a chance to review what we learnt about creating charts with two y-axes in Matplotlib and generating arrays with NumPy.

## Challenge 1

Are more prizes awarded recently than when the prize was first created? Show the trend in awards visually.

- Count the number of prizes awarded every year.
- Create a 5 year rolling average of the number of prizes (Hint: see previous lessons analyzing Google Trends).
- Using Matplotlib superimpose the rolling average on a scatter plot.
- Show a tick mark on the x-axis for every 5 years from 1900 to 2020. (Hint: you'll need to use NumPy).

![[2020-10-20_14-15-10-c99698bd9d7749499bb42a4763d446a6.png|500]]

- Use the [named colours](https://matplotlib.org/3.1.0/gallery/color/named_colors.html) to draw the data points in `dogerblue` while the rolling average is colored in `crimson`.

![[2020-10-20_14-15-24-c67d3b9baeaa22b2f28b6d3a2202d77a.png|500]]

- Looking at the chart, did the first and second world wars have an impact on the number of prizes being given out?
- What could be the reason for the trend in the chart?

## Challenge 2

Investigate if more prizes are shared than before.

- Calculate the average prize share of the winners on a year by year basis.
- Calculate the 5 year rolling average of the percentage share.
- Copy-paste the cell from the chart you created above.
- Modify the code to add a secondary axis to your Matplotlib chart.
- Plot the rolling average of the prize share on this chart.
- See if you can invert the secondary y-axis to make the relationship even more clear.