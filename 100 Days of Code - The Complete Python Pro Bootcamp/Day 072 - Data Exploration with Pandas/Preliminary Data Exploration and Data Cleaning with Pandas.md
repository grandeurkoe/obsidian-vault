# Preliminary Data Exploration and Data Cleaning with Pandas

Now that we've got our data loaded into our dataframe, we need to take a closer look at it to help us understand what it is we are working with. This is always the first step with any data science project. Let's see if we can answer the following questions: 

- How many rows does our dataframe have? 
- How many columns does it have?
- What are the labels for the columns? Do the columns have names?
- Are there any missing values in our dataframe? Does our dataframe contain any bad data?

We've already used the `.head()` method to peek at the top 5 rows of our dataframe. To see the number of rows and columns we can use the `shape` attribute:

`1. df.shape`

Do you see 51 rows and 6 columns printed out below the cell? 

We saw that each column had a name. We can access the column names directly with the `columns` attribute.

![[Pasted image 20231010124300.png|500]]
## Missing Values and Junk Data

Before we can proceed with our analysis we should try and figure out if there are any missing or junk data in our dataframe. That way we can avoid problems later on. In this case, we're going to look for NaN (Not A Number) values in our dataframe. NAN values are blank cells or cells that contain strings instead of numbers. Use the `.isna()` method and see if you can spot if there's a problem somewhere.

`1. df.isna()`

Did you find anything? Check the last couple of rows in the dataframe:

`1. df.tail()`

Aha! We have a row that contains some information regarding the source of the data with blank values for all the other other columns.

![[Pasted image 20231010124318.png|500]]

## Delete the Last Row

We don't want this row in our dataframe. There's two ways you can go about removing this row. The first way is to manually remove the row at index 50. The second way is to simply use the `.dropna()` method from pandas. Let's create a new dataframe without the last row and examine the last 5 rows to make sure we removed the last row:

```python
1. clean_df = df.dropna()
2. clean_df.tail()
```