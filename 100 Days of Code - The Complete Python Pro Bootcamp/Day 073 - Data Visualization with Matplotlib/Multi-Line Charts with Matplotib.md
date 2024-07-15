# Multi-Line Charts with Matplotib

What if we wanted to plot all the programming languages on the same chart? We don't want to type out .plot() a million times, right? We can actually just use a for-loop:

```python
for column in reshaped_df.columns:
	plt.plot(reshaped_df.index, reshaped_df[column])
```

This will allow us to iterate over each column in the DataFrame and plot it on our chart. The final result should look like this:

![[2020-09-23_15-44-25-e5665da7efcc5de7dca53f83f617ec15.png|500]]

But wait, which language is which? It's really hard to make out without a legend that tells us which color corresponds to each language. Let's modify the plotting code to add a label for each line based on the column name (and make the lines thicker at the same time using linewidth). Then let's add a legend to our chart:

```python
plt.figure(figsize=(16,10))
plt.xticks(fontsize=14)
plt.yticks(fontsize=14)
plt.xlabel('Date', fontsize=14)
plt.ylabel('Number of Posts', fontsize=14)
plt.ylim(0, 35000)

for column in reshaped_df.columns:
	plt.plot(reshaped_df.index, reshaped_df[column], linewidth=3,
	label=reshaped_df[column].name)

plt.legend(fontsize=16) 
```

We should now see something like this:

![[2020-09-23_16-23-20-177e4894db9a12e6c6369f2beaed4ccd.png|500]]