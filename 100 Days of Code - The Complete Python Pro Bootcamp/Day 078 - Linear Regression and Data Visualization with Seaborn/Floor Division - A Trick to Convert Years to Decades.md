# Floor Division: A Trick to Convert Years to Decades

In our bubble charts, we've seen how massively the industry has changed over time, especially from the 1970s onwards. This makes me think it makes sense to separate our films out by decade. Here's what I'm after:

![[2020-10-15_10-07-36-6a3655edec46115548a0f09bbd8b1173.png|500]]

## Challenge

Can you create a column in `data_clean` that has the decade of the movie release. For example, a film released in 1992 or 1999 should have 1990 in the Decade column.

Here is one approach that you can follow:

1. Create a [`DatetimeIndex` object](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DatetimeIndex.html) from the `Release_Date` column.

![[2020-10-16_10-59-13-2ca82264854d799c5ea7a9aac7246b85.png|500]]

2. Grab all the years from the `DatetimeIndex` object using the `.year` property.
3. Use floor division `//` to convert the year data to the decades of the films.
4. Add the decades as a `Decade` column to the `data_clean` DataFrame.

## Solution: Using Floor Division to Convert Years to Decades

To create a DatetimeIndex, we just call the constructor and provide our release date column as an argument to initialise the DatetimeIndex object. Then we can extract all the years from the DatetimeIndex.

```python
1. dt_index = pd.DatetimeIndex(data_clean.Release_Date)
2. years = dt_index.year
```

Now, all we need to do is convert the years to decades. For that, we will use floor division (aka integer division). The difference to regular division is that the result is effectively rounded down.

```python
1. 5.0 / 2
2. # output: 2.5
3. 5.0 // 2
4. # output: 2.0
```

In our case, we will use the floor division by 10 and then multiplication by 10 to convert the release year to the release decade:

![[2020-10-16_11-13-38-ea1ff36ff1f36d1b44616077685626e5.png|500]]

We can do this for all the years and then add the decades back as a column.

```python
1. decades = years//10*10
2. data_clean['Decade'] = decades
```