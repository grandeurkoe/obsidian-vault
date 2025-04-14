# Grouping and Pivoting Data with Pandas

Often times you will want to sum rows that belong to a particular category. For example, which category of degrees has the highest average salary? Is it STEM, Business or HASS (Humanities, Arts, and Social Science)? 

To answer this question we need to learn to use the `.groupby()` method. This allows us to manipulate data similar to a Microsoft Excel Pivot Table.

We have three categories in the 'Group' column: STEM, HASS and Business. Let's count how many majors we have in each category:

`clean_df.groupby('Group').count()`

## Mini Challenge

Now can you use the `.mean()` method to find the average salary by group? 

![[Pasted image 20231010123857.png|500]]

Here's the solution:

![[Pasted image 20231010123938.png|500]]
## Number formats in the Output

The above is a little hard to read, isn't it? We can tell Pandas to print the numbers in our notebook to look like 1,012.45 with the following line:

`pd.options.display.float_format = '{:,.2f}'.format`

![[2020-09-22_14-49-50-81fee388ca0de81b4f791e6481392d76.png|500]]