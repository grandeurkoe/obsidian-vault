# Sorting Values & Adding Columns - Majors with the Most Potential vs Lowest Risk

## Lowest Risk Majors

A low-risk major is a degree where there is a small difference between the lowest and highest salaries. In other words, if the difference between the 10th percentile and the 90th percentile earnings of your major is small, then you can be more certain about your salary after you graduate.

How would we calculate the difference between the earnings of the 10th and 90th percentile? Well, Pandas allows us to do simple arithmetic with entire columns, so all we need to do is take the difference between the two columns:

`clean_df['Mid-Career 90th Percentile Salary'] - clean_df['Mid-Career 10th Percentile Salary']`

Alternatively, you can also use the `.subtract()` method.

`clean_df['Mid-Career 90th Percentile Salary'].subtract(clean_df['Mid-Career 10th Percentile Salary'])`

The output of this computation will be another Pandas dataframe column. We can add this to our existing dataframe with the `.insert()` method:

```python
1. spread_col = clean_df['Mid-Career 90th Percentile Salary'] - clean_df['Mid-Career 10th Percentile Salary']
2. clean_df.insert(1, 'Spread', spread_col)
3. clean_df.head()
```

The first argument is the position of where the column should be inserted. In our case, it's at position 1, so the second column.

![[2020-09-22_14-10-35-1520a94db77897101844ff463324112a.png|500]]

## Sorting by the Lowest Spread

To see which degrees have the smallest spread, we can use the `.sort_values()` method. And since we are interested in only seeing the name of the degree and the major, we can pass a list of these two column names to look at the `.head()` of these two columns exclusively.

```python
1. low_risk = clean_df.sort_values('Spread')
2. low_risk[['Undergraduate Major', 'Spread']].head()
```

Does `.sort_values()` sort in ascending or descending order? To find out, check out the Pandas documentation:  [https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.sort_values.html](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.sort_values.html)

You can also bring up the quick documentation with SHIFT + TAB on your keyboard directly in the Python notebook.

![[2020-09-22_14-24-40-22d0a938ccc70fca5e8f74e0dc194148.gif|500]]