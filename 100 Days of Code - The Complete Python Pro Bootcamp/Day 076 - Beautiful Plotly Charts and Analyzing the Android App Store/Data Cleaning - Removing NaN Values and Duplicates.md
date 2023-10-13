# Data Cleaning: Removing NaN Values and Duplicates

## Preliminary Data Exploration

Compared to the previous projects we are working with a fairly large DataFrame this time.

```python
1. df_apps.shape
```

tells us we have 10841 rows and 12 columns.

![[2020-10-10_11-42-00-2dbe2416526a6711a2ba703aac9d4841.png|500]]

We can already see that there are some data issues that we need to fix. In the Ratings and Type columns there are NaN (Not a number values) and in the Price column we have dollar signs that will cause problems.

The `.sample(n)` method will give us n random rows. This is another handy way to inspect our DataFrame.

![[2020-10-10_11-42-49-6f7378014bb37376d36b47f735e53063.png|500]]