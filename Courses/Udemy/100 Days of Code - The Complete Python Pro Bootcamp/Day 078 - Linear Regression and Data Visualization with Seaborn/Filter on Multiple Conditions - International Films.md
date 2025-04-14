# Filter on Multiple Conditions: International Films

So far, we've created subsets for our DataFrame based on a single condition. But what if we want to select our data based on more than one condition? For example, which films made money internationally (i.e., `data.USD_Worldwide_Gross != 0`), but had zero box office revenue in the United States (i.e., `data.USD_Domestic_Gross == 0`)? 

How would we create a filter for these two conditions? One approach is to use the `.loc[]` property combined with the [bitwise and](https://docs.python.org/3.4/library/operator.html#mapping-operators-to-functions) `&` operator.

```python
1. international_releases = data.loc[(data.USD_Domestic_Gross == 0) & 
2.                                   (data.USD_Worldwide_Gross != 0)]
```

Why does this work? Pandas is built on top of NumPy, which uses Python's bitwise operators. And these bitwise operators allow us to do comparisons on an element by element basis in both NumPy and Pandas! Here's an example:

![[2020-10-14_18-25-38-1acab27e5b6c677db5828de681d34cbe.png|500]]

However, we're also checking if the domestic revenue was zero and the worldwide revenue was not zero. Because the bitwise operator takes precedence, we need to include parentheses `()` around the comparisons we'd like to prioritize.

![[2020-10-14_18-30-07-f144e3467424b4262de238f33db8917e.png|500]]

However, this is not the only technique we can use to make multiple comparisons.

## Challenge

Use the Pandas [`.query()` function](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.query.html) to accomplish the same thing. Create a subset for international releases that had some worldwide gross revenue, but made zero revenue in the United States.

Hint: This time you'll have to use the `and` keyword.

## Solution: Using the .query() function to filter on multiple conditions

In this case, we enclose the entire query inside a string.

```python
1. international_releases = data.query('USD_Domestic_Gross == 0 and USD_Worldwide_Gross != 0')
2. print(f'Number of international releases: {len(international_releases)}')
3. international_releases.tail()
```

The column names are recognized and we see the following:

![[2020-10-14_18-34-38-3cdecd04820328d2020a3300f5bab57c.png|500]]

## Unreleased Films

Now we can turn our attention to films in the dataset that were not released at the time the data was collected. This is why films like Singularity and Aquaman had zero revenue.

## Challenge

- Identify which films were not released yet as of the time of data collection (May 1st, 2018).
- How many films are included in the dataset that have not yet had a chance to be screened in the box office? 
- Create another DataFrame called `data_clean` that does not include these films.

## Solution

There are a total of 7 unreleased films at the time of data collection included in the dataset.

![[2020-10-14_18-46-19-04127ebc60d12d2a5eb14800bbfd7a7a.png|500]]

From this point on, we'll work with another DataFrame called `data_clean` that does not include these films.

`1. data_clean = data.drop(future_releases.index)`

## Challenge: Films that Lost Money

Having removed the unreleased films entirely can you calculate the percentage of films that did not break even at the box office? We already saw that more than the bottom quartile of movies appears to lose money when we ran `.describe()`. However, what is the true percentage of films where the costs exceed the worldwide gross revenue?

## Solution: Budget greater than revenue

Again, there are different ways you could have calculated this. For example, using the `.loc[]` property,

```python
1. money_losing = data_clean.loc[data_clean.USD_Production_Budget > data_clean.USD_Worldwide_Gross]
2. len(money_losing)/len(data_clean)
```

or the `.query()` function

```python
1. money_losing = data_clean.query('USD_Production_Budget > USD_Worldwide_Gross')
2. money_losing.shape[0]/data_clean.shape[0]
```

In both cases, we see that a whopping 37.2% 😮 of films do not recoup their production budget at the box office. 💸💸💸 Who knew that film finance could be so risky! 😬