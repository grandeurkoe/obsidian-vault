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

## Solution 1: Preliminary Data Exploration

When we run `df_data.shape`, `df_data.tail()`, and `df_data.head()`, we see that there are 962 rows and 16 columns. The first Nobel prizes were awarded in 1901 and the data goes up to 2020.

![[2020-10-20_11-00-28-1798f7e1537c4a5e3a5197eb6411a12b.png|500]]

We notice that the columns contain the following information:

**birth_date**: date in string format

**motivation**: description of what the prize is for

**prize_share**: given as a fraction

**laureate_type:** individual or organisation

**birth_country**: has countries that no longer exist

**birth_country_current**: current name of the country where the birth city is located

**ISO:** three-letter international country code

**organization_name**: research institution where the discovery was made

**organization_city:** location of the institution

## Solution 2: NaN values

There are no duplicates in the dataset:

`1. print(f'Any duplicates? {df_data.duplicated().values.any()}')`

However, there are a number of NaN values

`1. print(f'Any NaN values among the data? {df_data.isna().values.any()}')
`
We can get a count of the NaN values per column using

`1. df_data.isna().sum()`

![[2020-10-20_11-10-39-9f5107ed7f79742d98c60af382a4a4e7.png|500]]

Why are there so many NaN values for the birth date? And why are there so many missing values among the organisation columns?

Filtering on the NaN values in the birth date column we see that we get back a bunch of organizations, like the UN or the Red Cross.

```python
1. col_subset = ['year','category', 'laureate_type',
2.               'birth_date','full_name', 'organization_name']
3. df_data.loc[df_data.birth_date.isna()][col_subset]
```