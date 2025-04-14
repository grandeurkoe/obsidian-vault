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

## Dropping Unused Columns and Removing NaN Values

To remove the unwanted columns, we simply provide a list of the column names `['Last_Updated', ‘Android_Ver']` to the `.drop()` method. By setting `axis=1` we are specifying that we want to drop certain columns.

![[2020-10-10_11-46-45-e0bba8ef961e0d55342aa3015415781f.png|500]]

To find and remove the rows with the NaN values we can create a subset of the DataFrame based on where `.isna()` evaluates to `True`. We see that NaN values in ratings are associated with no reviews (and no installs). That makes sense.

![[2020-10-10_11-46-58-0b80c76b8e494af654b061e730950323.png|500]]

We can drop the NaN values with `.dropna()`:

```python
1. df_apps_clean = df_apps.dropna()
2. df_apps_clean.shape
```

This leaves us with 9,367 entries in our DataFrame.

## Finding and Removing Duplicates

There are indeed duplicates in the data. We can show them using the `.duplicated()` method, which brings up 476 rows:

```python
1. duplicated_rows = df_apps_clean[df_apps_clean.duplicated()]
2. print(duplicated_rows.shape)
3. duplicated_rows.head()
```

We can actually check for an individual app like ‘Instagram’ by looking up all the entries with that name in the App column.

![[2020-10-10_11-47-31-8c3f03dbcb7dd1fe7d38c6cc96a69a9a.png|500]]

So how do we get rid of duplicates? Can we simply call `.drop_duplicates()`?

`1. df_apps_clean = df_apps_clean.drop_duplicates()`

Not really. If we do this without specifying how to identify duplicates, we see that 3 copies of Instagram are retained because they have a different number of reviews. We need to provide the column names that should be used in the comparison to identify duplicates. For example:

![[2020-10-10_11-47-48-eb3f1b28243622d449e0958bc57ad4a5.png|500]]

This leaves us with 8,199 entries after removing duplicates. Huzzah! 💪

## What else should I know about the data?

So we can see that 13 different features were originally scraped from the Google Play Store.

- Obviously, the data is just a sample out of all the Android apps. It doesn't include all Android apps of which there are millions.
- I’ll assume that the sample is representative of the App Store as a whole. This is not necessarily the case as, during the web scraping process, this sample was served up based on geographical location and user behavior of the person who scraped it - in our case Lavanya Gupta.
- The data was compiled around 2017/2018. The pricing data reflect the price in USD Dollars at the time of scraping. (developers can offer promotions and change their app’s pricing).
- I’ve converted the app’s size to a floating-point number in MBs. If data was missing, it has been replaced by the average size for that category.
- The installs are not the exact number of installs. If an app has 245,239 installs then Google will simply report an order of magnitude like 100,000+. I’ve removed the '+' and we’ll assume the exact number of installs in that column for simplicity.

Here’s what you would see under an Android app listing if you go to a listing on the Google Play Store:

![[2020-10-10_11-48-11-f6ba2e6e8c46047d93a8c2d1baaa68d1.png|500]]

![[2020-10-10_11-48-18-97ccd1a03fd69d43ea1a1635e1e521d8.png|500]]