# Accessing Columns and Individual Cells in a Dataframe

## Find College Major with Highest Starting Salaries

To access a particular column from a data frame we can use the square bracket notation, like so:

`clean_df['Starting Median Salary']`

![[2020-09-22_11-43-02-a2d17fe32f141cfc42f3b7c60d7b646c.png|500]]

To find the highest starting salary we can simply chain the .max() method.

`clean_df['Starting Median Salary'].max()`

The highest starting salary is $74,300. But which college major earns this much on average? For this, we need to know the row number or index so that we can look up the name of the major. Lucky for us, the .idxmax() method will give us index for the row with the largest value.

`clean_df['Starting Median Salary'].idxmax()`

which is 43. To see the name of the major that corresponds to that particular row, we can use the .loc (location) property.

`clean_df['Undergraduate Major'].loc[43]`

Here we are selecting both a column ('Undergraduate Major') and a row at index 43, so we are retrieving the value of a particular cell. You might see people using the double square brackets notation to achieve exactly the same thing: 

`clean_df['Undergraduate Major'][43]`

![[2020-09-22_11-56-10-07043fb3a8bb6a9f4fd3e5d17f4319d5.png|500]]

If you don't specify a particular column you can use the .loc property to retrieve an entire row:

`clean_df.loc[43]`

![[2020-09-22_11-58-08-1c59109dc860ad3b4571bc492a16445b.png|500]]

## Challenge

Now that we've found the major with the highest starting salary, can you write the code to find the following:

- What college major has the highest mid-career salary? How much do graduates with this major earn? (Mid-career is defined as having 10+ years of experience).
- Which college major has the lowest starting salary and how much do graduates earn after university?
- Which college major has the lowest mid-career salary and how much can people expect to earn with this degree?

### The Highest Mid-Career Salary

```python
1. print(clean_df['Mid-Career Median Salary'].max())
2. print(f"Index for the max mid career salary: {clean_df['Mid-Career Median Salary'].idxmax()}")
3. clean_df['Undergraduate Major'][8]
```

If you have multiple lines in the same cell, only the last one will get printed as an output automatically. If you'd like to see more than one thing printed out, then you still have to use a print statement on the lines above.

### The Lowest Starting and Mid-Career Salary

```python
1. print(clean_df['Starting Median Salary'].min())
2. clean_df['Undergraduate Major'].loc[clean_df['Starting Median Salary'].idxmin()]
```

Here I've nested the code that we've seen in the previous lesson in the same line. We can also use the `.loc` property to access an entire row. Below I've accessed the row at the index of the smallest mid-career salary:

`1. clean_df.loc[clean_df['Mid-Career Median Salary'].idxmin()]`

Sadly, education is actually the degree with the lowest mid-career salary and Spanish is the major with the lowest starting salary.

![[2021-01-20_11-23-21-bdd958d133438e5c99c0a870acb03764.png|500]]