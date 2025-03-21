# Data Visualization - Bitcoin: Line Style and Markers

Now that we've got Tesla looking the way we want it to, let's do the same for Bitcoin. We've already matched the sample frequency and we can re-use our chart! Simply copy-paste the entire cell and make some modifications to the code as per the challenge.

## Challenge

1. Modify the chart title to read 'Bitcoin News Search vs Resampled Price'
2. Change the y-axis label to 'BTC Price'
3. Change the y- and x-axis limits to improve the appearance
4. Investigate the [linestyles](https://matplotlib.org/3.2.1/api/_as_gen/matplotlib.pyplot.plot.html) to make the BTC closing price a dashed line
5. Investigate the [marker types](https://matplotlib.org/3.2.1/api/markers_api.html) to make the search datapoints little circles
6. Were big increases in searches for Bitcoin accompanied by big increases in the price?

The end result should look something like this:

![[2020-10-10_11-09-03-5dca1c064a53e55e7aeaf5ff44c77f29.png|500]]

## Solution

I hope you had a good go at generating the chart.

Updating the title and the axis labels just involved changing the strings. To set the axis limits, I've chosen $0 to $15,000 on the left y-axis. I've also used a HEX code for orange to color the line.

To change the line style or the markers, you just have to look at the documentation (e.g., try `'--'` or `'-.'` for the `linestyle`). Similarly for the markers, you also have loads of different options:

![[2020-10-10_11-09-23-859e1afde86b85212030553a87efb08f.png|500]]

I think the main trick with this challenge involved substituting a different set of dates. The months of the time series are found in the index of the monthly bitcoin prices: `df_btc_monthly.index`.

```python
1. plt.figure(figsize=(14,8), dpi=120)

3. plt.title('Bitcoin News Search vs Resampled Price', fontsize=18)
4. plt.xticks(fontsize=14, rotation=45)

6. ax1 = plt.gca()
7. ax2 = ax1.twinx()

9. ax1.set_ylabel('BTC Price', color='#F08F2E', fontsize=14)
10. ax2.set_ylabel('Search Trend', color='skyblue', fontsize=14)

12. ax1.xaxis.set_major_locator(years)
13. ax1.xaxis.set_major_formatter(years_fmt)
14. ax1.xaxis.set_minor_locator(months)

16. ax1.set_ylim(bottom=0, top=15000)
17. ax1.set_xlim([df_btc_monthly.index.min(), df_btc_monthly.index.max()])

19. # Experiment with the linestyle and markers
20. ax1.plot(df_btc_monthly.index, df_btc_monthly.CLOSE, 
21.          color='#F08F2E', linewidth=3, linestyle='--')
22. ax2.plot(df_btc_monthly.index, df_btc_search.BTC_NEWS_SEARCH, 
23.          color='skyblue', linewidth=3, marker='o')

25. plt.show()
```

What we see in the chart is that similar to Tesla, the crazy price movements in the beginning of 2018 are associated with very high search volumes. Everyone was talking about (and buying) Bitcoin in late 2017/early 2018 so search volumes were at a record high!  Interestingly, there was quite a huge spike in bitcoin prices in Q1 of 2019, but this time the increase in search volume was much less pronounced (perhaps because at this point everyone knew what Bitcoin was).

![[2020-10-10_11-09-40-6f411b90cb8b323b628cec8b171f4f66.png|500]]

## Solution 1: Number of Prizes Awarded over Time

First, we have to count the number of Nobel prizes that are awarded each year.

`1. prize_per_year = df_data.groupby(by='year').count().prize `

This just involves grouping the data so that we can count the number of entries per year. To calculate the 5-year moving average we use `.rolling()` and `.mean()` like we did with the Google Trend data.

`1. moving_average = prize_per_year.rolling(window=5).mean()`

Now we can create a Matplotlib chart that superimposes the two:

```python
1. plt.scatter(x=prize_per_year.index, 
2.            y=prize_per_year.values, 
3.            c='dodgerblue',
4.            alpha=0.7,
5.            s=100,)
6.
7. plt.plot(prize_per_year.index, 
8.         moving_average.values, 
9.         c='crimson', 
10.         linewidth=3,)
11.
12. plt.show()
```

![[2020-10-20_14-23-51-6e82d0a2a593ae5f05b2562d18daed03.png]]

With the help of a little styling, this chart could look better. To create 5-year tick marks on the x-axis, we generate an array using NumPy:

`1. np.arange(1900, 2021, step=5)`

Then we tap into functions like the `.figure()`, the `.title()`, the `.xticks()`, and `.yticks()` to fine-tune the chart.

In addition, we will shortly be adding a second y-axis, so we can use an `Axes` object to draw our scatter and line plots.

```python
1. plt.figure(figsize=(16,8), dpi=200)
2. plt.title('Number of Nobel Prizes Awarded per Year', fontsize=18)
3. plt.yticks(fontsize=14)
4. plt.xticks(ticks=np.arange(1900, 2021, step=5), 
5.            fontsize=14, 
6.            rotation=45)
7.
8. ax = plt.gca() # get current axis
9. ax.set_xlim(1900, 2020)
10.
11. ax.scatter(x=prize_per_year.index, 
12.            y=prize_per_year.values, 
13.            c='dodgerblue',
14.            alpha=0.7,
15.            s=100,)
16
17. ax.plot(prize_per_year.index, 
18.         moving_average.values, 
19.         c='crimson', 
20.         linewidth=3,)
21.
22. plt.show()
```

![[2020-10-20_14-20-53-0c21b93b7886ff45ea6503747813ff1c.png|500]]
