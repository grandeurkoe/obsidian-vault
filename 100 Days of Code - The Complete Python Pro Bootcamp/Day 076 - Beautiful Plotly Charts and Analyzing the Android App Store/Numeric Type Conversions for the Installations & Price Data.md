# Numeric Type Conversions for the Installations & Price Data

#### Challenge

How many apps had over 1 billion (that's right - BILLION) installations? How many apps just had a single install?

1. Check the datatype of the Installs column.
2. Count the number of apps at each level of installations.
3. Convert the number of installations (the Installs column) to a numeric data type. Hint: this is a 2-step process. You'll have to make sure you remove non-numeric characters first.

## Data Cleaning & Converting Data to Numeric Types

To check the data types you can either use `.describe()` on the column or `.info()` on the DataFrame.

![[2020-10-11_12-24-39-fb2db75e5e71a3e89c859e35ad516032.png|500]]

Both of these show that we are dealing with a non-numeric data type. In this case, the type is "object".

If we take two of the columns, say Installs and the App name, we can count the number of entries per level of installations with `.groupby()` and `.count()`. However, because we are dealing with a non-numeric data type, the ordering is not helpful. The reason Python is not recognizing our installs as numbers is because of the comma (`,`) characters.

![[2020-10-11_12-25-56-6e1796e77c7c62d86add95c5bb702d61.png|500]]

We can remove the comma (`,`) character - or any character for that matter - from a DataFrame using the string’s [.replace()](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.Series.str.replace.html) method. Here we’re saying: “replace the `,` with an empty string”. This completely removes all the commas in the Installs column. We can then convert our data to a number using `.to_numeric()`.

```python
1. df_apps_clean.Installs = df_apps_clean.Installs.astype(str).str.replace(',', "")
2. df_apps_clean.Installs = pd.to_numeric(df_apps_clean.Installs)
3. df_apps_clean[['App', 'Installs']].groupby('Installs').count()
```

![[2020-10-11_12-27-06-b8d1d316afdae7047bd4c37d3c1bd0ab.png|500]]

#### Challenge

Convert the price column to numeric data. Then investigate the top 20 most expensive apps in the dataset.

Remove all apps that cost more than $250 from the `df_apps_clean` DataFrame.

Add a column called '`Revenue_Estimate`' to the DataFrame. This column should hold the price of the app times the number of installs. What are the top 10 highest-grossing paid apps according to this estimate? Out of the top 10, how many are games?

## Finding the most Expensive Apps and Filtering out the Junk


If you look at the data type of the price column:

`1. df_apps_clean.Price.describe()`

You also see that is of type object. The reason is the dollar $ signs that we’ve spotted before. To convert the price column to numeric data we use the .replace() method once again, but this time we filter out the dollar sign.

```python
1. df_apps_clean.Price = df_apps_clean.Price.astype(str).str.replace('$', "")
2. df_apps_clean.Price = pd.to_numeric(df_apps_clean.Price)
3.
4. df_apps_clean.sort_values('Price', ascending=False).head(20)
```

Here’s what we see:

![[2020-10-11_12-29-17-bc5f0a4ad2e83b4d4fcf62a84f7f3511.png|500]]

What’s going on here? There are 15 I am Rich Apps in the Google Play Store apparently. They all cost $300 or more, which is the main point of the app. The story goes that in 2008, Armin Heinrich released the very first I am Rich app in the iOS App Store for $999.90. The app does absolutely nothing. It just displays the picture of a gemstone and can be used to prove to your friends how rich you are. Armin actually made a total of 7 sales before the app was hastily removed by Apple. Nonetheless, it inspired a bunch of copycats on the Android App Store, but if you search today, you’ll find all of these apps have disappeared as well. The high installation numbers are likely gamed by making the app was available for free at some point to get reviews and appear more legitimate.

![[2020-10-11_12-29-36-4a5ef8c85b0be30fd61421016efa78db.png|500]]

Leaving this bad data in our dataset will misrepresent our analysis of the most expensive 'real' apps. Here’s how we can remove these rows:

```python
1. df_apps_clean = df_apps_clean[df_apps_clean['Price'] < 250]
2. df_apps_clean.sort_values('Price', ascending=False).head(5)
```

When we look at the top 5 apps now, we see that 4 out of 5 are medical apps.

![[2020-10-11_12-30-28-ab771a555e152a1f12150951f5cb06b4.png|500]]

We can work out the highest grossing paid apps now. All we need to do is multiply the values in the price and the installs column to get the number:

1. df_apps_clean['Revenue_Estimate'] = df_apps_clean.Installs.mul(df_apps_clean.Price)
2. df_apps_clean.sort_values('Revenue_Estimate', ascending=False)[:10]

This generously assumes of course that all the installs would have been made at the listed price, which is unlikely, as there are always promotions and free give-aways on the App Stores.