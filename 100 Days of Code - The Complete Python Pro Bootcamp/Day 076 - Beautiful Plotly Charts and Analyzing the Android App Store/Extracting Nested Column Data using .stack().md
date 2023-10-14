# Extracting Nested Column Data using .stack()

Let’s turn our attention to the Genres column. This is quite similar to the categories column but more granular.

## Challenge

How many different types of genres are there? Can an app belong to more than one genre? Check what happens when you use `.value_counts()` on a column with nested values? See if you can work around this problem by using the `.split()` function and the DataFrame [.stack() method](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.stack.html).

