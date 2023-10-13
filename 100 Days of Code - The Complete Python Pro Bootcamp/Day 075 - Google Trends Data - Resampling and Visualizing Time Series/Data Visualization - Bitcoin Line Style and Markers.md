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