# Visualise the Number of Sets Published over Time

Now let's take a look at how many sets the LEGO company has published year-on-year. This might tell us something about how LEGO's product offering has changed over time.

First, let's import Matplotlib so we can visualise our findings up top:

![[2020-10-10_10-04-25-4662afd292f45dad36aef7cbcceb27f5.png|500]]

## Challenge

Now, let's create a new Series called `sets_by_year` which has the years as the index and the number of sets as the value. The result should look something like this:

![[2020-10-10_10-04-52-141876d03b94367866b783a03a6b1ab3.png|500]]

Having summed the number of LEGO sets per year, visualise this data using a line chart with Matplotlib. You should get something like this:

![[2020-10-10_10-05-12-d674a354dd6f26e5c23d3d85c9aac8d1.png|500]]

Because the .csv file is from late 2020, to plot the full calendar years, you will have to exclude some data from your chart. Use the slicing techniques covered in Day 21 to avoid plotting the last two years? The same syntax will work on Pandas DataFrame. You should get this:

![[2020-10-10_10-05-25-812d7e5f957add390f4211666f4ea87c.png|500]]

## Solution

The trick is grouping the data by the year and counting the number of entries for that year.

![[2020-10-10_10-06-25-14a269ee27054a41394bbe99d62e3b73.png|500]]

From this, we can see that LEGO published less than 10 different sets per year during its first few years of operation. But by 2019 the company had grown spectacularly, releasing 840 sets in that year alone!

You also notice that there is an entry for 2021. The .csv file is from late 2020, so it appears that it already includes some sets on a forward-looking basis. We'll have to take this into account for our charts:

`1. plt.plot(sets_by_year.index, sets_by_year.set_num)`

If we don't exclude the last two years we get a dramatic drop at the end of the chart. This is quite misleading as it suggests LEGO is in big trouble! Given the dataset does not include a full calendar year for 2020, it's best to exclude the last two rows to get a better picture:

`1. plt.plot(sets_by_year.index[:-2], sets_by_year.set_num[:-2])`

The Python List slicing syntax covered in Day 21 comes in quite handy here!

![[2020-10-10_10-06-43-b657ffe5b3d7feb7ce6ffc4b910b2830.png|500]]

We also see that while the first 45 years or so, LEGO had some steady growth in its product offering, but it was really in the mid-1990s that the number of sets produced by the company increased dramatically! We also see a brief decline in the early 2000s and a strong recovery around 2005 in the chart.