# Using Locators and DateFormatters to generate Tick Marks on a Time Line

## Adding Locator Tick Marks

When working with time series, it's often quite difficult to get the tick marks on charts looking the way you want to. This is why we have Locator helpers.

Using Locators we can change our x-axis from looking like this:

![[2020-10-10_10-57-39-2376090b467db02dceb424bf07223dc7.png|500]]

to looking like this:

![[2020-10-10_10-57-46-18d3f3b6a5aeb054538191a6e2bcdc45.png|500]]

The first step is importing `matplotlib.dates`.  This is where all the date plotting capabilities live.

![[2020-10-10_10-57-57-dca144954b405981349fa0bbaf4e4ceb.png|500]]

Next, we need a `YearLocator()` and a `MonthLocator()` objects, which will help Matplotlib find the years and the months. Then we also need a `DateFormatter()`, which will help us specify how we want to display the dates.

![[2020-10-10_10-58-15-23bb49c679afbcc94ae30cea8c083a34.png|500]]

Now we can go back to our chart and format where the major and minor ticks should be using the Locators.

```python
1. # format the ticks
2. ax1.xaxis.set_major_locator(years)
3. ax1.xaxis.set_major_formatter(years_fmt)
4. ax1.xaxis.set_minor_locator(months)
```

The final outcome should now look like this: