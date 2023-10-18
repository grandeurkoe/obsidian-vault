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

8. fig.update_traces(textposition='inside', textfont_size=15, textinfo='percent')

10. fig.show()
```

![[2020-10-20_11-56-24-23e01a3883d76f0a36dd62e0ad401479.png|500]]

## Solution 3: The first 3 women to win

Even without looking at the data, you might have already guessed one of the famous names: Marie Curie.

`1. df_data[df_data.sex == 'Female'].sort_values('year', ascending=True)[:3]`

![[2020-10-20_11-59-16-2880c50d998356973cfa975e30bd642c.png|500]]

