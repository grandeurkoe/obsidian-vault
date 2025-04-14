# Find the Oldest and Largest LEGO Sets

## Markdown Challenge Solution

Here's how you'd organize the markdown cells with the section headings and image tags. You might have also spotted that enclosing text in the double-asterisk ** symbol will make it bold.

![[2020-10-10_10-00-46-a944be269cd20332fd94d895450df735.png|500]]

## Exploring the sets.csv

The sets.csv contains a list of LEGO sets. It shows in which year the set was released and the number of parts in the set.

Can you take the first steps in exploring this dataset? Read the .csv and take a look at the columns.

Then try and answer the following questions:

- In which year were the first LEGO sets released and what were these sets called?
- How many different products did the LEGO company sell in their first year of operation?
- What are the top 5 LEGO sets with the most number of parts?

The first step as always is reading the .csv file and looking what's in it. We see that there's some sort of id for each set (the `set_num`), the name of the set, the year in which it was released, the `theme_id` (the code for the theme name) and the number of parts.

So it looks like we have everything we here to answer our two questions.

![[2020-10-10_10-02-02-a972bf2ca76f191c7f91524738051393.png|500]]

To find the year when the first LEGO sets were released we have to sort by the year column. The [.sort_values()](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.sort_values.html?highlight=sort_values#pandas.DataFrame.sort_values) method will by default sort in ascending order.

![[2020-10-10_10-02-11-9144c07c8cd3b0d8c84a8bab2f2ad570.png|500]]

Looks like LEGO started all the way back in 1949! 😮 The names for these sets are nothing to write home about, but let's find out how many different products the company was selling in their first year since launch:

![[2020-10-10_10-02-21-1a8072e9810feffcc47084f852c42fe2.png|500]]

Back in 1949, LEGO got started selling only 5 different sets! Note that here we are filtering our DataFrame on a **condition**. We are retrieving the rows where the year column has the value 1949: `sets['year'] == 1949`.

Now let's find the LEGO set with the largest number of parts. If we want to find the largest number of parts, then we have to set the `ascending` argument to `False` when we sort by the `num_parts` column.

![[2020-10-10_10-02-49-93522b13c73c23d3ed869086ce139e84.png|500]]

The largest LEGO set ever produced has around 10,000 pieces! Apparently, only two of these boxes were ever produced, so if you wanted to get your hands on a ridiculously large LEGO set, you'll have to settle for the 7,541 piece Millennium Falcon.