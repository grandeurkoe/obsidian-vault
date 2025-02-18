# Data Visualization - Unemployment: The Effect of New Data

The financial crisis in 2008 was pretty bad. We saw how it took around 10 years for the unemployment rate to go back to where it was prior to the crisis.

Let's see how 2020 affects our analysis.

## Challenge

Read the data in the 'UE Benefits Search vs UE Rate 2004-20.csv' into a DataFrame. Convert the MONTH column to Pandas Datetime objects and then plot the chart. What do you see?

## Solution

Here's how you read the data and make a DataFrame:

```python
1. df_ue_2020 = pd.read_csv('UE Benefits Search vs UE Rate 2004-20.csv')
2. df_ue_2020.MONTH = pd.to_datetime(df_ue_2020.MONTH)

And here's the chart:

1. plt.figure(figsize=(14,8), dpi=120)
2. plt.yticks(fontsize=14)
3. plt.xticks(fontsize=14, rotation=45)
4. plt.title('Monthly US "Unemployment Benefits" Web Search vs UNRATE incl 2020', fontsize=18)

6. ax1 = plt.gca()
7. ax2 = ax1.twinx()

9. ax1.set_ylabel('FRED U/E Rate', color='purple', fontsize=16)
10. ax2.set_ylabel('Search Trend', color='skyblue', fontsize=16)

12. ax1.set_xlim([df_ue_2020.MONTH.min(), df_ue_2020.MONTH.max()])

14. ax1.plot(df_ue_2020.MONTH, df_ue_2020.UNRATE, 'purple', linewidth=3)
15. ax2.plot(df_ue_2020.MONTH, df_ue_2020.UE_BENEFITS_WEB_SEARCH, 'skyblue', linewidth=3)

17. plt.show()
```

What we see is not pretty. The US unemployment rate spiked to unprecedented levels during the COVID pandemic, dwarfing the levels seen during the financial crisis. Let's hope the recovery will be swifter this time.

![[2020-10-10_11-14-12-32b356c73fc9f6654195ac97aaf8155e.png|500]]