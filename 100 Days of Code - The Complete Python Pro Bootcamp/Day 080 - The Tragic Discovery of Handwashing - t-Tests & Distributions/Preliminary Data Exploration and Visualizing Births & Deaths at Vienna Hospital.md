# Preliminary Data Exploration and Visualizing Births & Deaths at Vienna Hospital

You (aka Dr Semmelweis) are working at Vienna General Hospital. Let's take a closer look at the data you've been collecting on the number of births and maternal deaths throughout the 1840s.

![[2020-10-23_10-38-09-9527e9a9d46107327b4fa76246c62b81.png|500]]

## Challenge 1: Preliminary Data Exploration

- What is the shape of `df_yearly` and `df_monthly`? How many rows and columns?
- What are the column names?
- Which years are included in the dataset?
- Are there any NaN values or duplicates?
- What were the average number of births that took place per month?
- What were the average number of deaths that took place per month?

## Solution to Challenge 1

Using `.shape`, `.head()`, `.tail()` we see that the dataset covers the years 1841 to 1849. The two tables report the total number of births and the total number of deaths. Interestingly, the yearly data breaks the number of births and deaths down by clinic.

![[2020-10-23_10-42-54-fb1af5f4e2bd231b283dabdaca8cc4c3.png|500]]

We see that there are no NaN values in either of the DataFrames. We can verify this either with using `.info()` or using `.isna().values.any()`.

![[2020-10-23_10-47-41-c48e37522afaa8f220c19a26a4c7ab73.png|500]]

There are also no duplicate entries. In other words, the dataset appears to be clean.

![[2020-10-23_10-48-41-6018a072a58ca120945dab55dbbdc651.png|500]]

Using `.describe()` allows us to view some interesting statistics at a glance. We see that on average there were about 267 births and 22.47 deaths per month.

![[2020-10-23_10-52-34-6870fc442c6051d51df38af7904c328b.png|500]]

## Challenge 2: Percentage of Women Dying in Childbirth

How dangerous was childbirth in the 1840s in Vienna?

- Using the annual data, calculate the percentage of women giving birth who died throughout the 1840s at the hospital.

In comparison, the United States recorded 18.5 maternal deaths per 100,000 or 0.018% in 2013 [(source).](https://en.wikipedia.org/wiki/Maternal_death#:~:text=The%20US%20has%20the%20%22highest,17.8%20per%20100%2C000%20in%202009)

## Solution to Challenge 2

Childbirth was very risky! About 7.08% of women died 💀 in the 1840s (compared to 0.018% in the US in 2013).

```python
1. prob = df_yearly.deaths.sum() / df_yearly.births.sum() * 100
2. print(f'Chances of dying in the 1840s in Vienna: {prob:.3}%')
```

If someone gave me a bag of 100 M&Ms and told me that 7 of them would kill me, I'd (probably) pass on those M&Ms 🤭. Just saying.

#### Challenge 3: Visualise the Total Number of Births 🤱 and Deaths 💀 over Time

Create a [Matplotlib chart](https://matplotlib.org/3.3.2/api/_as_gen/matplotlib.pyplot.plot.html) with twin y-axes. It should look something like this:

![[2020-10-23_11-06-31-76e4e6fbe90cd4edb47e9dee6eb3da5f.png|500]]

- Format the x-axis using locators for the years and months (Hint: we did this in the Google Trends notebook)
- Set the range on the x-axis so that the chart lines touch the y-axes
- Add gridlines
- Use `skyblue` and `crimson` for the line colors
- Use a dashed line style for the number of deaths
- Change the line thickness to 3 and 2 for the births and deaths respectively.
- Do you notice anything in the late 1840s?