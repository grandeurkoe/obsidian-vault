# Data Manipulation: Pivoting DataFrame

## The `.pivot()` method

Sometimes you want to convert your DataFrame so that each category has its own column. For example, suppose you needed to take the table below and create a separate column for each actor, where each row is the Age of the actor:

![[2020-09-23_14-13-02-d87f678153b7f925e4fba57d50e6be42.png|500]]

How would you do this with the DataFrame below?

```python
test_df = pd.DataFrame({'Age': ['Young', 'Young', 'Young', 'Young', 'Old', 'Old', 'Old', 'Old'], 'Actor': ['Jack', 'Arnold', 'Keanu', 'Sylvester', 'Jack', 'Arnold', 'Keanu', 'Sylvester'], 'Power': [100, 80, 25, 50, 99, 75, 5, 30]})
test_df
```

The easiest way to accomplish this is by using the `.pivot()` method in Pandas. Try the example for yourself. The thing to understand is how to supply the correct arguments to get the desired outcome. The index are the categories for the rows. The columns are the categories for the columns. And the values are what you want in the new cells. 

```python
pivoted_df = test_df.pivot(index='Age', columns='Actor', values='Power')
pivoted_df
```

However, there's one very important thing to notice. What happens if a value is missing? In the example above there's no value for old Sylvester. In this case, the .pivot() method will insert a NaN value.

### Mini-Challenge

- Can you pivot the `df` DataFrame so that each row is a date and each column is a programming language? Store the result under a variable called `reshaped_df`. 
- Examine the dimensions of the reshaped DataFrame. How many rows does it have? How many columns?
- Examine the head and the tail of the DataFrame. What does it look like?
- Print out the column names.
- Count the number of entries per column.

You should get something like this:

![[2020-09-23_14-27-55-8546c808e45a701c9bdeda01a143b6ee.png|500]]

### Solution

Here's how you pivot our existing DataFrame to get the outcome above:

`1. reshaped_df = df.pivot(index='DATE', columns='TAG', values='POSTS')`

![[2020-09-23_14-31-18-670a7feecfbf419b590b726011272d6b.png|500]]

We have 145 rows and 14 columns in the new DataFrame. Each programming language became a column and our date column became the new index (i.e., the label for the rows).

When we count the number of entries per column we see that not all languages are the same. The reason is that the .count() method excludes NaN values. When we pivoted the DataFrame the NaN values were inserted when there were no posts for a language in that month (e.g., Swift in July, 2008).

![[2020-09-23_14-34-29-8c9748278d5ebf22fe5c302f168b2374.png|500]]
## Dealing with NaN Values

In this case, we don't want to drop the rows that have a NaN value. Instead, we want to substitute the number 0 for each NaN value in the DataFrame. We can do this with the `.fillna()` method.

`reshaped_df.fillna(0, inplace=True) `

The `inplace` argument means that we are updating `reshaped_df`. Without this argument we would have to write something like this:

`reshaped_df = reshaped_df.fillna(0)`

Let's check if we successfully replaced all the NaN values in our DataFrame.

![[2020-10-10_09-29-00-fc06492f23b6024594050f7035777e10.png|500]]

We can also check if there are any NaN values left in the entire DataFrame with this line:

`reshaped_df.isna().values.any()`

Here we are using the `.isna()` method that we've used before, but we're chaining two more things: the `values` attribute and the `any()` method. This means we don't have to search through the entire DataFrame to spot if `.isna()` is True.

![[2020-10-10_09-29-22-32eddb02d5f95698f34a2a77356b8c80.png|500]]

Now we're all set to create some charts and visualize our data.