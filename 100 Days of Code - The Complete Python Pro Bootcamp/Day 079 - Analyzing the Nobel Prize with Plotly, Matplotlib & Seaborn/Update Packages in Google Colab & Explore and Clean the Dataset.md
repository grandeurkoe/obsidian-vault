# Update Packages in Google Colab & Explore and Clean the Dataset

## Using Google Colab? -> Upgrade Plotly

Google Colab comes with a lot of Python packages pre-installed and working. However, you can also install new packages as well as upgrade existing packages. In our case, the Plotly package is outdated and will cause a problem with our starburst chart. Here's how to updated a package in Google Colab:

![[2020-10-20_10-48-06-906d5f7f29d10c2385370daad3032c87.gif|500]]

Uncomment the cell with the pip install command. Run the cell. And then comment the code out again.

## Challenge 1

Preliminary data exploration.

- What is the shape of `df_data`? How many rows and columns?
- What are the column names and what kind of data is inside of them?
- In which year was the Nobel prize first awarded?
- Which year is the latest year included in the dataset?

## Challenge 2

- Are there any duplicate values in the dataset?
- Are there NaN values in the dataset?
- Which columns tend to have NaN values?
- How many NaN values are there per column?
- Why do these columns have NaN values?

## Challenge 3

- Convert the `birth_date` column to Pandas `Datetime` objects
- Add a Column called `share_pct` which has the laureates' share as a percentage in the form of a floating-point number.