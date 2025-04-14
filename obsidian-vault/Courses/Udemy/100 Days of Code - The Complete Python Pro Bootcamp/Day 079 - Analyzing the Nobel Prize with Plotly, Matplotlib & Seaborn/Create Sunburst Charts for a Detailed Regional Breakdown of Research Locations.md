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

## Solution 2: Research Cities

```python
1. top20_org_cities = df_data.organization_city.value_counts()[:20]
2. top20_org_cities.sort_values(ascending=True, inplace=True)
3. city_bar2 = px.bar(x = top20_org_cities.values,
4.                   y = top20_org_cities.index,
5.                   orientation='h',
6.                   color=top20_org_cities.values,
7.                   color_continuous_scale=px.colors.sequential.Plasma,
8.                   title='Which Cities Do the Most Research?')
9.
10. city_bar2.update_layout(xaxis_title='Number of Prizes', 
11.                        yaxis_title='City',
12.                        coloraxis_showscale=False)
13. city_bar2.show()
```

Cambridge Massachusetts and New York in the United States lead the pack:

![[2020-10-20_16-33-45-b33d120ab774aace3fda3b522a405341.png|500]]

## Solution 3: Laureate Birth Cities

```python
1. top20_cities = df_data.birth_city.value_counts()[:20]
2. top20_cities.sort_values(ascending=True, inplace=True)
3. city_bar = px.bar(x=top20_cities.values,
4.                   y=top20_cities.index,
5.                   orientation='h',
6.                   color=top20_cities.values,
7.                   color_continuous_scale=px.colors.sequential.Plasma,
8.                   title='Where were the Nobel Laureates Born?')
9.
10. city_bar.update_layout(xaxis_title='Number of Prizes', 
11.                        yaxis_title='City of Birth',
12.                        coloraxis_showscale=False)
13. city_bar.show()
```

A higher population definitely means that there's a higher chance of a Nobel laureate to be born there. New York, Paris, and London are all very populous. However, Vienna and Budapest are not and still produced many prize winners. That said, much of the ground-breaking research does not take place in big population centers, so the list of birth cities is quite different from the list above. Cambridge Massachusetts, Stanford, Berkeley and Cambridge (UK) are all the places where many discoveries are made, but they are not the birthplaces of laureates.

![[2020-10-20_16-40-44-6ffe0befd6b184a767c184fb64906fda.png|500]]

## Solution 4: The Sunburst Chart

Each country has a number of cities, which contain a number of cities, which in turn contain the research organizations. The sunburst chart is perfect for representing this relationship. It will give us an idea of how geographically concentrated scientific discoveries are!

```python
1. country_city_org = df_data.groupby(by=['organization_country', 
2.                                        'organization_city', 
3.                                        'organization_name'], as_index=False).agg({'prize': pd.Series.count})
4.
5. country_city_org = country_city_org.sort_values('prize', ascending=False)
```

![[2020-10-20_16-43-55-88d224f6d6086a8e9231579966fde144.png|500]]

```python
1. burst = px.sunburst(country_city_org, 
2.                     path=['organization_country', 'organization_city', 'organization_name'], 
3.                     values='prize',
4.                     title='Where do Discoveries Take Place?',
5.                    )
6.
7. burst.update_layout(xaxis_title='Number of Prizes', 
8.                     yaxis_title='City',
9.                     coloraxis_showscale=False)
10.
11. burst.show()
```

France is a great example of concentration. Practically all the organisations affiliated with Nobel prize winners are in Paris. In contrast, scientific discoveries are much more spread out across Germany. Meanwhile, the UK is dominated by Cambridge and London.

![[2020-10-20_16-47-52-801621189ef9ffc4c83025bac35b9861.gif|500]]