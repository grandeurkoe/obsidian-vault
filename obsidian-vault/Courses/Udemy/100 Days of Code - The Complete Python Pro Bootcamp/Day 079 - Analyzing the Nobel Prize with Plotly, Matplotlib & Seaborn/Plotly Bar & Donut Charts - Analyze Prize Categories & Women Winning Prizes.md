# Plotly Bar & Donut Charts - Analyze Prize Categories & Women Winning Prizes

## Challenge 1: Come up with 3 Questions

A big part of data science is coming up with questions that you'd like to explore. This is the most difficult aspect to teach in a tutorial because it's completely open-ended and requires some creativity. Often times you will be asking questions of the data, that it actually cannot answer - and that's ok. That's all part of the process of discovery.

Pause here for a moment and think about the kind of data you saw in the columns. Write down at least 3 questions that you'd like to explore as part of this analysis. For example, your question might go like: "What percentage of the Nobel laureates were women?" or "How many prizes were given out in each category". **Practice coming up with a few of your own questions**.

In the upcoming lessons, you might find that we will write the code to answer some of your questions. And if not, your questions make for a great exercise to take this analysis even further.

The challenges below are all based on questions we're going to ask the data:

## Challenge 2

Create a [donut chart using plotly](https://plotly.com/python/pie-charts/) which shows how many prizes went to men compared to how many prizes went to women. What percentage of all the prizes went to women?

## Challenge 3

- What are the names of the first 3 female Nobel laureates?
- What did the win the prize for?
- What do you see in their `birth_country`? Were they part of an organization?

## Challenge 4

Did some people get a Nobel Prize more than once? If so, who were they?

## Challenge 5

- In how many categories are prizes awarded?
- Create a Plotly bar chart with the number of prizes awarded by category.
- Use the color scale called `Aggrnyl` to color the chart, but don't show a color axis.
- Which category has the most number of prizes awarded?
- Which category has the fewest number of prizes awarded?

## Challenge 6

- When was the first prize in the field of Economics awarded?
- Who did the prize go to?

## Challenge 7

Create a [plotly bar chart](https://plotly.com/python/bar-charts/) that shows the split between men and women by category.

- Hover over the bar chart. How many prizes went to women in Literature compared to Physics?

![[2020-10-20_11-50-28-39415361f3c46d2884316bad464b6aa6.png|500]]

## Solution 2: Creating a Donut Chart with Plotly

To create the chart we use the our `.value_counts()` method together with Plotly's `.pie()` function. We see that out of all the Nobel laureates since 1901, only about 6.2% were women.

```python
1. biology = df_data.sex.value_counts()
2. fig = px.pie(labels=biology.index, 
3.              values=biology.values,
4.              title="Percentage of Male vs. Female Winners",
5.              names=biology.index,
6.              hole=0.4,)
7.
8. fig.update_traces(textposition='inside', textfont_size=15, textinfo='percent')
9.
10. fig.show()
```

![[2020-10-20_11-56-24-23e01a3883d76f0a36dd62e0ad401479.png|500]]

## Solution 3: The first 3 women to win

Even without looking at the data, you might have already guessed one of the famous names: Marie Curie.

`1. df_data[df_data.sex == 'Female'].sort_values('year', ascending=True)[:3]`

![[2020-10-20_11-59-16-2880c50d998356973cfa975e30bd642c.png|500]]

## Solution 4: The Repeat Winners

Winning a Nobel prize is quite an achievement. However, some folks have actually won the prize multiple times. To find them, we can use many different approaches. One approach is to look for duplicates in the full_name column:

```python
1. is_winner = df_data.duplicated(subset=['full_name'], keep=False)
2. multiple_winners = df_data[is_winner]
3. print(f'There are {multiple_winners.full_name.nunique()}' \
4.       ' winners who were awarded the prize more than once.')
```

There are 6 winners who were awarded the prize more than once.

```python
1. col_subset = ['year', 'category', 'laureate_type', 'full_name']
2. multiple_winners[col_subset]
```

Only 4 of the repeat laureates were individuals.

![[2020-10-20_12-04-43-b5e52b86991f0ee6b5fd0c49ee6e0d3d.png|500]]

We see that Marie Curie actually got the Nobel prize twice - once in physics and once in chemistry. Linus Carl Pauling got it first in chemistry and later for peace given his work in promoting nuclear disarmament. Also, the International Red Cross was awarded the Peace prize a total of 3 times. The first two times were both during the devastating World Wars.

## Solution 5: Number of Prizes per Category

To find the number of unique categories in a column we can use:

`1. df_data.category.nunique()`

To generate the vertical Plotly bar chart, we again use `.value_counts()`:

```python
1. prizes_per_category = df_data.category.value_counts()
2. v_bar = px.bar(
3.         x = prizes_per_category.index,
4.         y = prizes_per_category.values,
5.         color = prizes_per_category.values,
6.         color_continuous_scale='Aggrnyl',
7.         title='Number of Prizes Awarded per Category')

9. v_bar.update_layout(xaxis_title='Nobel Prize Category', 
10.                     coloraxis_showscale=False,
11.                     yaxis_title='Number of Prizes')
12. v_bar.show()
```

![[2020-10-20_13-59-47-6fea83b45bae6cda8e421d02b71aa380.png|500]]

## Solution 6: The Economics Prize

The chart above begs the question: "Why are there so few prizes in the field of economics?". Looking at the first couple of winners in the economics category, we have our answer:

`1. df_data[df_data.category == 'Economics'].sort_values('year')[:3]`

The economics prize is much newer. It was first awarded in 1969, compared to 1901 for physics.

![[2020-10-20_14-03-25-9b4e50252c31bbc38d8171905a26b9a5.png|500]]

## Solution 7: Male and Female Winners by Category

We already saw that overall, only 6.2% of Nobel prize winners were female. Does this vary by category?

```python
1. cat_men_women = df_data.groupby(['category', 'sex'], 
2.                                as_index=False).agg({'prize': pd.Series.count})
3. cat_men_women.sort_values('prize', ascending=False, inplace=True)
```

We can combine `.groupby()` and `.agg()` with the `.count()` function. This way we can count the number of men and women by prize category.

![[2020-10-20_14-06-59-34c0d756c22989eb982fcf00dd78bcff.png|500]]

We can then use `.color` the parameter in the `.bar()` function to mark the number of men and women on the chart:

```python
1. v_bar_split = px.bar(x = cat_men_women.category,
2.                      y = cat_men_women.prize,
3.                      color = cat_men_women.sex,
4.                      title='Number of Prizes Awarded per Category split by Men and Women')

6. v_bar_split.update_layout(xaxis_title='Nobel Prize Category', 
7.                           yaxis_title='Number of Prizes')
8. v_bar_split.show()
```

![[2020-10-20_14-09-23-ba9b59621175ffd123d135b4cd46fed5.png|500]]

We see that overall the imbalance is pretty large with physics, economics, and chemistry. Women are somewhat more represented in categories of Medicine, Literature and Peace. Splitting bar charts like this is an incredibly powerful way to show a more granular picture.