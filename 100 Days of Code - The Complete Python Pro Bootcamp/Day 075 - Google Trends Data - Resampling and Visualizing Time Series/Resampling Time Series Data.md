# Resampling Time Series Data

## Finding the missing values

For 3 of the DataFrame there are no missing values. We can verify this using the `.isna()` method. This will return a whole series of Booleans, but we can chain `.values.any()` to see if any value in the series is `True`.

```python
1. print(f'Missing values for Tesla?: {df_tesla.isna().values.any()}')
2. print(f'Missing values for U/E?: {df_unemployment.isna().values.any()}')
3. print(f'Missing values for BTC Search?: {df_btc_search.isna().values.any()}')
```

However, for the Bitcoin price data, there seems to be a problem. There's a missing value somewhere.

The number of missing values can be found by using `.sum()` to add up the number of occurrences of `True` in the series. This shows that there are 2 missing values.

To find the row where the missing values occur, we can create a subset of the DataFrame using `.isna()` once again (If you've arrived at this answer using a different approach, that's fine too. There are a number of ways to solve this challenge.)

![[2020-10-10_10-39-35-0b1e488850a4c761254ddbe93fef69e0.png|500]]

To remove a missing value we can use `.dropna()`. The `inplace` argument allows to overwrite our DataFrame and means we don't have to write:

```python
1. df_btc_price = df_btc_price.dropna()
```

## Converting Strings to DateTime Objects

All the date data in our columns are in the form of strings. To convert this into a Datetime object we're going to use the Pandas `.to_datetime()` function.

```python
1. df_tesla.MONTH = pd.to_datetime(df_tesla.MONTH)
2. df_btc_search.MONTH = pd.to_datetime(df_btc_search.MONTH)
3. df_unemployment.MONTH = pd.to_datetime(df_unemployment.MONTH)
4. df_btc_price.DATE = pd.to_datetime(df_btc_price.DATE)`
```

![[2020-10-10_10-40-14-4fb3d5f631ceaea60b7dc9f2de1ec533.png|500]]

## Resampling Time Series Data

Next, we have to think about how to make our Bitcoin price and our Bitcoin search volume comparable. Our Bitcoin price is daily data, but our Bitcoin Search Popularity is monthly data.

To convert our daily data into monthly data, we're going to use the [.resample()](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.resample.html) function. The only things we need to specify is which column to use (i.e., our DATE column) and what kind of sample frequency we want (i.e., the "rule"). We want a monthly frequency, so we use `'M'`.  If you ever need to resample a time series to a different frequency, you can find a list of different options [here](https://pandas.pydata.org/pandas-docs/stable/user_guide/timeseries.html#dateoffset-objects) (for example `'Y'` for yearly or `'T'` for minute).

After resampling, we need to figure out how the data should be treated. In our case, we want the last available price of the month - the price at month-end.

```python
1. df_btc_monthly = df_btc_price.resample('M', on='DATE').last()
```

If we wanted the average price over the course of the month, we could use something like:

```python
1. df_btc_monthly = df_btc_price.resample('M', on='DATE').mean()
```

This is what our data looks like now: