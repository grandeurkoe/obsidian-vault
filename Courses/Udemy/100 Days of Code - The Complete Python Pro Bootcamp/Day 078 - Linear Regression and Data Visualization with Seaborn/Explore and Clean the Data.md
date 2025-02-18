# Explore and Clean the Data

## Challenge 1

Answer these questions about how the data is structured:

1. How many rows and columns does the dataset contain?
2. Are there any NaN values present?
3. Are there any duplicate rows?
4. What are the data types of the columns?

## Challenge 2

Convert the `USD_Production_Budget`, `USD_Worldwide_Gross`, and `USD_Domestic_Gross` columns to a numeric format by removing `$` signs and `,`.

Note that _domestic_ in this context refers to the United States.

## Challenge 3

Convert the `Release_Date` column to a Pandas Datetime type.

## Solution 1

With any new dataset, it's a good idea to do some standard checks and conversions. I typically always first look at `.shape`, `.head()`, `.tail()`, `.info()` and `.sample()`.  Here's what I'm spotting already:

![[2020-10-14_14-46-28-63dd3d1025bbcd51f2effa33132c48f0.png|500]]

There are thousands of entries in the DataFrame - one entry for each movie. We'll have some challenges formatting the data before we can do more analysis because we have non-numeric characters in our budget and revenue columns.

We can check for NaN values with this line:

`1. data.isna().values.any()`

And check for duplicates with this line:

`1. data.duplicated().values.any()`

We can see the total number of duplicates by creating a subset and looking at the length of that subset:

```python
1. duplicated_rows = data[data.duplicated()]
2. len(duplicated_rows)
```

![[2020-10-14_14-51-20-7ae3dea5e27c5d9ea9d7e26b9bdddc36.png|500]]

The fact that there are no duplicates or NaN (not-a-number) values in the dataset will make our job easier. We can also see if there are null values in `.info()`, which also shows us that we need to do some type conversion.

![[2020-10-14_14-54-47-6c35659efd0a6ebd03bde9de6851e72c.png|500]]

## Solution 2

In order to convert the data in the budget and revenue columns and remove all the non-numeric characters, we can use a nested for loop. We create two Python lists: the characters to remove and the column names. Inside the nested loop we can combine `.replace()` and `.to_numeric()` to achieve our goal.

```python
1. chars_to_remove = [',', '$']
2. columns_to_clean = ['USD_Production_Budget', 
3.                     'USD_Worldwide_Gross',
4.                     'USD_Domestic_Gross']

6. for col in columns_to_clean:
7.     for char in chars_to_remove:
8.         # Replace each character with an empty string
9.         data[col] = data[col].astype(str).str.replace(char, "")
10.     # Convert column to a numeric data type
11.     data[col] = pd.to_numeric(data[col])
```

![[2020-10-14_15-01-32-a70628a70ce1a0f946a2a760132323ba.png|500]]

## Solution 3

To convert the Release_Date column to a DateTime object, all we need to do is call the `to_datetime()` function.

`1. data.Release_Date = pd.to_datetime(data.Release_Date)`

When we check `.info()` again we see that the columns now have the desired data type. This allows us to proceed with the next parts of our analysis.

![[2020-10-14_15-06-08-862b621b9dfc92e9110a1619e0da56ee.png|500]]