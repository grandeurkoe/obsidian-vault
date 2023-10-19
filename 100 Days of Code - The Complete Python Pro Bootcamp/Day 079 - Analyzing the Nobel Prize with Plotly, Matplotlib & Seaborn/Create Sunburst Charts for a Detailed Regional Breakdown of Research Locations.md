# Create Sunburst Charts for a Detailed Regional Breakdown of Research Locations

## Challenge 1

Many Nobel laureates are affiliated with a university, a laboratory, or a research organization (apart from Literature and Peace prize winners as we've seen). But the world is a big place. Which research institutions had the most Nobel laureates working there at the time of making the discovery?

Create a bar chart showing the organizations affiliated with the Nobel laureates. It should looks something like this:

![[2020-10-20_16-18-43-4bf4936075c466a83bf4fee81d4bcbd5.png|500]]

- Which organizations make up the top 20?
- How many Nobel prize winners are affiliated with the University of Chicago and Harvard University?

## Challenge 2

Each research organization is located in a particular city. Are some cities hot spots for scientific discoveries? Where do major discoveries tend to take place?

- Create another Plotly bar chart graphing the top 20 organization cities of the research institutions associated with a Nobel laureate.
- Where is the number one hotspot for discoveries in the world?
- Which city in Europe has had the most discoveries?

## Challenge 3

Contrast the above chart with the birth city of the Nobel laureates. Would you expect to see a similar ranking for where the laureates are born versus where most discoveries are made? Would you expect to see the most populous cities producing the highest number of Nobel laureates? 

- Create a Plotly bar chart graphing the top 20 birth cities of Nobel laureates.
- Use a named color scale called `Plasma` for the chart.
- What percentage of the United States prizes came from Nobel laureates born in New York?
- How many Nobel laureates were born in London, Paris and Vienna?
- Out of the top 5 cities, how many are in the United States?

## Challenge 4

- Create a DataFrame that groups the number of prizes by organization.
- Then use the [plotly documentation to create a sunburst chart](https://plotly.com/python/sunburst-charts/)
- Click around in your chart, what do you notice about Germany and France?

Here's what you're aiming for:

![[2020-10-20_16-28-14-33e9e87ab3c8bed913f451342e7af3fe.png|500]]

## Solution 1: The Top Research Organizations

This one should be pretty simple:

```python
1. top20_orgs = df_data.organization_name.value_counts()[:20]
2. top20_orgs.sort_values(ascending=True, inplace=True)
```

Our chart includes many of the usual suspects:

```python
1. org_bar = px.bar(x = top20_orgs.values,
2.                  y = top20_orgs.index,
3.                  orientation='h',
4.                  color=top20_orgs.values,
5.                  color_continuous_scale=px.colors.sequential.haline,
6.                  title='Top 20 Research Institutions by Number of Prizes')
7.
8. org_bar.update_layout(xaxis_title='Number of Prizes', 
9.                       yaxis_title='Institution',
10.                       coloraxis_showscale=False)
11. org_bar.show()
```

![[2020-10-20_16-32-06-e8df8d97281819d8f0359c11bac9bfb8.png|500]]

