# Data Visualisation - Tesla Line Charts in Matplotlib

## Creating a basic chart

To create a line plot with two different y-axes we first have to get the current axis and make a copy of it using `.twinx()`. Then we can configure each axis separately and call `.plot()`.

```python
1. ax1 = plt.gca() # get current axis
2. ax2 = ax1.twinx()

4. ax1.set_ylabel('TSLA Stock Price')
5. ax2.set_ylabel('Search Trend')

7. ax1.plot(df_tesla.MONTH, df_tesla.TSLA_USD_CLOSE)
8. ax2.plot(df_tesla.MONTH, df_tesla.TSLA_WEB_SEARCH)
```

![[2020-10-10_10-49-05-1179a1661d9c361d9c12017b41ec184d.png|500]]

## Adding colors

Your code should now look something like this (with your own choice of colors of course):

```python
1. ax1 = plt.gca()
2. ax2 = ax1.twinx()

4. ax1.set_ylabel('TSLA Stock Price', color='#E6232E') # can use a HEX code
5. ax2.set_ylabel('Search Trend', color='skyblue') # or a named colour

7. ax1.plot(df_tesla.MONTH, df_tesla.TSLA_USD_CLOSE, color='#E6232E')
8. ax2.plot(df_tesla.MONTH, df_tesla.TSLA_WEB_SEARCH, color='skyblue')
```

![[2020-10-10_10-50-06-b58773f5e0d68af73e2f86ed98d2e0bb.png|500]]

## Additional styling, increasing size & resolution

There's a couple of tweaks to the code going on here. First, we use `.figure()` to increase the size and resolution of our chart. Since we now have a bigger chart, we should also increase the font size of our labels and the thickness of our lines.

Finally, we are calling `.show()` to explicitly display the chart below the cell. This `.show()` method is important to be aware of if you're ever trying to generate charts in PyCharm or elsewhere outside of an interactive notebook like Google Colab or Jupyter. Also, it gives our notebook a very clean look.

```python
1. # increases size and resolution
2. plt.figure(figsize=(14,8), dpi=120) 
3. plt.title('Tesla Web Search vs Price', fontsize=18)

5. ax1 = plt.gca()
6. ax2 = ax1.twinx()

8. # Also, increase fontsize and linewidth for larger charts
9. ax1.set_ylabel('TSLA Stock Price', color='#E6232E', fontsize=14)
10. ax2.set_ylabel('Search Trend', color='skyblue', fontsize=14)

12. ax1.plot(df_tesla.MONTH, df_tesla.TSLA_USD_CLOSE, color='#E6232E', linewidth=3)
13. ax2.plot(df_tesla.MONTH, df_tesla.TSLA_WEB_SEARCH, color='skyblue', linewidth=3)

15. # Displays chart explicitly
16. plt.show()
```

![[2020-10-10_10-51-47-d5990af9c5e8865734f7cf3b9b148e7f.png|500]]

Here's the code with rotation added to the x-ticks. With `.set_ylim()` and `.set_xlim()` you have precise control over which data you want to show on the chart. You can either choose hard values like displaying the Tesla stock price between $0 and $600. Or you could use the `.min()` and `.max()` functions to help you work out the bounds for the chart as well.

```python
1. plt.figure(figsize=(14,8), dpi=120)
2. plt.title('Tesla Web Search vs Price', fontsize=18)

4. # Increase the size and rotate the labels on the x-axis
5. plt.xticks(fontsize=14, rotation=45)

7. ax1 = plt.gca()
8. ax2 = ax1.twinx()

10. ax1.set_ylabel('TSLA Stock Price', color='#E6232E', fontsize=14)
11. ax2.set_ylabel('Search Trend', color='skyblue', fontsize=14)

13. # Set the minimum and maximum values on the axes
14. ax1.set_ylim([0, 600])
15. ax1.set_xlim([df_tesla.MONTH.min(), df_tesla.MONTH.max()])

17. ax1.plot(df_tesla.MONTH, df_tesla.TSLA_USD_CLOSE, color='#E6232E', linewidth=3)
18. ax2.plot(df_tesla.MONTH, df_tesla.TSLA_WEB_SEARCH, color='skyblue', linewidth=3)

20. plt.show()
```

## Fix the Matplotlib Warning (if you see it)

At this point, you might have seen this warning below from Matplotlib:

![[2020-10-10_10-53-19-7dbefe134f91b1ef45472f11e8c3897a.png|500]]

This is not an error, but an FYI to be explicit about which datetime converter to use. We have a timeline on our x-axis after all. To address this simply follow the instructions in the warning message and add the following code:

![[2020-10-10_10-53-10-163ce2a670fec6820f2670f1f577b98c.png|500]]