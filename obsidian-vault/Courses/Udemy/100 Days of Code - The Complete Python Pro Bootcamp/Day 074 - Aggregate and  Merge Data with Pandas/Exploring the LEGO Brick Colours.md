# Exploring the LEGO Brick Colors

## Import Pandas

As always, the first step is importing the module that we'll use: Pandas

`1. import pandas as pd`

## Examine the Structure

From there we can read the .csv file and take a look at the first 5 rows.

```python
1. colors = pd.read_csv('data/colors.csv')
2. colors.head()
```

We see that there are 5 columns, which include the name of the color and its corresponding RGB value. To find the number of unique colors, all we need to do is check if every entry in the `name` column is unique: 

`1. colors['name'].nunique()`

This shows us that there are 135 unique colors for LEGO blocks.

![[2020-10-10_09-58-28-fcec4fff9f8de20b986d2724fc943ed1.png|500]]

## Find the number of transparent colors

One way you can do this is through combining our old friend, the .groupby() method, with the .count() method.

`1. colors.groupby('is_trans').count() `

Here we just group by the `is_trans` column and count the entries.

But you might have also come across the very handy [.value_counts()](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.Series.value_counts.html) method in your research.

`1. colors.is_trans.value_counts()`

Once again, we select the column (here with the .dot notation) and call the method. The `.value_counts(`) method is a very quick way of finding the number of members of each category.

![[2020-10-10_09-59-01-72c5f6806993e7aac3b70b004f68cfe9.png|500]]

## Challenge

Do you remember how to work with section headings and images? See if you can tackle the next couple of challenges to make your notebook look like this:

![[2020-10-10_09-59-18-bb72700801f816440f58289b5658841c.png|500]]

