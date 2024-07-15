# Data Cleaning: Working with Time Stamps

## Selecting an Individual Cell

Let's take a closer look at the 'DATE' column in our DataFrame. We can use the double square bracket notation to look at the second entry in the column: 

`1. df['DATE'][1]`

Alternatively, for column names no spaces, we can also use the dot-notation:

`1. df.DATE[1]`

I prefer the square bracket notation for column names since it's more flexible, but with the dot notation, you get to use autocomplete, which is also nice.

![[2020-09-23_11-56-27-154946ab0ee26941481e132d488e3049.png|500]]

## Inspecting the Data Type

When we type check the contents of this cell, we see that we are not dealing with a date object, but rather with a string.

![[2020-09-23_11-58-49-85cfb3f4fd4167f591789e228b718b16.png|500]]

This is not very handy. Not only will the string format always show the unnecessary 00:00:00, but we also don't get the benefit of working with Datetime objects, which know how to handle dates and times. Pandas can help us convert the string to a timestamp using the [to_datetime()](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.to_datetime.html) method.

Here's how we can convert the entry in our cell and check that it worked:

![[2020-09-23_13-43-08-b0e4ee7ca77200303a59fd33923b3847.png|500]]

Let's use Pandas' `to_datetime()` to convert the entire `df['DATE']` column.

![[2020-09-23_13-49-24-59422ce38b28d0ca79ac20c33f208996.png|500]]

