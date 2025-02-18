# Upload the Data and Read the .csv File

Download the salaries_by_college_major.csv file from the course resources and add this file to the notebook by dropping it into the sidebar with the little folder icon.

![[2020-09-22_10-45-21-1d02a75826ee94fcef5aef04e10931ed.gif|500]]

Then import pandas into your notebook and read the .csv file. 

```python
1. import pandas as pd
2. df = pd.read_csv('salaries_by_college_major.csv')
```

You can save yourself some typing by bringing up the autocompletion by using the keyboard shortcuts ctrl + Space (windows) or ⌘ + Space (Mac).

![[2020-09-22_11-09-31-5eb5efad427d845c7d65a7510d80fd68.gif|500]]

Now take a look at the Pandas dataframe we've just created with .head(). This will show us the first 5 rows of our dataframe.

`df.head()`

Once you hit shift + enter on your keyboard the cell will be evaluated and you should see the output automatically printed below the cell. This feature of automatically printing the output below in a pretty format is what makes the notebook format so lovely to work with.

![[2020-09-22_11-06-57-1d11d7f059838b14ceb2288b5148ffe4.png|500]]