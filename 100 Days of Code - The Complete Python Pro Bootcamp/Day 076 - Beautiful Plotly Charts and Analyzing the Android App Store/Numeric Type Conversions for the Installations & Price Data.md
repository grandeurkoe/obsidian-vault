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