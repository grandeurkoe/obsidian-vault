# Accessing Columns and Individual Cells in a Dataframe

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