# Preliminary Data Exploration

First, we import pandas and then we can call read_csv(), where we can provide some additional arguments, like the names for our columns.

`1. df = pd.read_csv('QueryResults.csv', names=['DATE', 'TAG', 'POSTS'], header=0)`

Setting the header row to 0 allows us to substitute our own column names.

![[2020-09-23_11-23-29-0c30461310d1fcb810742b60eb0c2e2b.png|500]]

Next, we use `.head()` and `.tail()` to look at the first and last 5 rows. This allows us to verify that our column naming worked as intended.

![[2020-09-23_11-25-50-4d27fccc068255a1dfb2975a747119c8.png|500]]

To check the dimensions of the DataFrame, we use our old friend `.shape`. This tells us we have 1991 rows and 3 columns.

![[2020-09-23_11-28-30-83282ebe527d6a76e74dbd146590e92e.png]]