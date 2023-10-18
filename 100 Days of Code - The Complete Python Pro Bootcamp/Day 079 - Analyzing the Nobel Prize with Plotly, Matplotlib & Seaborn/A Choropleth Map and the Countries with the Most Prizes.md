# A Choropleth Map and the Countries with the Most Prizes

For this next bit, we're going to compare which countries actually get the most prizes. And we're also going to look at in which categories those prizes are awarded. This has me feeling a little like I'm at the Olympics 😊.

## Challenge 1: Top 20 Country Ranking

- Create a Pandas DataFrame called `top20_countries` that has the two columns. The `prize` column should contain the total number of prizes won.

![[2020-10-20_14-42-59-9fb704fd63feff9b691697416ea5c722.png|500]]

- Is it best to use `birth_country`, `birth_country_current` or `organization_country`?
- What are some potential problems when using `birth_country` or any of the others? Which column is the least problematic?
- Then use Plotly to create a horizontal bar chart showing the number of prizes won by each country. Here's what you're after:

![[2020-10-20_14-43-26-c29a036da3674550eb3e9879a6f1b3a6.png|500]]

- What is the ranking for the top 20 countries in terms of the number of prizes?

## Challenge 2: Choropleth Map

- Create this choropleth map using [the plotly documentation](https://plotly.com/python/choropleth-maps/):

![[2020-10-20_14-44-57-c9ec3018035c0e32588e167a8e8b0a00.png|500]]

- Experiment with [plotly's available colours](https://plotly.com/python/builtin-colorscales/). I quite like the sequential color `matter` on this map.

Hint: You'll need to use a 3 letter country code for each country.

## Challenge 3: Country Bar Chart with Prize Category

See if you can divide up the Plotly bar chart you created above to show the which categories made up the total number of prizes. Here's what you're aiming for:

![[2020-10-20_15-11-40-896b68120f5e2daa0e2823f286619336.png|500]]

- In which category are Germany and Japan the weakest compared to the United States?
- In which category does Germany have more prizes than the UK?
- In which categories does France have more prizes than Germany?
- Which category makes up most of Australia's Nobel prizes?
- Which category makes up half of the prizes in the Netherlands?
- Does the United States have more prizes in Economics than all of France? What about in Physics or Medicine?

The hard part is preparing the data for this chart!

_Hint_: Take a two-step approach. The first step is grouping the data by country and category. Then you can create a DataFrame that looks something like this:

![[2020-10-20_15-11-54-d06c71c4976b32b66b2bef08144cb67a.png|500]]

## Challenge 4: Prizes by Country over Time

Every country's fortunes wax and wane over time. Investigate how the total number of prizes awarded changed over the years.

- When did the United States eclipse every other country in terms of the number of prizes won?
- Which country or countries were leading previously?
- Calculate the cumulative number of prizes won by each country in every year. Again, use the `birth_country_current` of the winner to calculate this.
- Create a [plotly line chart](https://plotly.com/python/line-charts/) where each country is a colored line.

## Solution 1: Prize ranking by Country

Looking at our DataFrame there are actually 3 different columns to choose from for creating this ranking: `birth_country`, `birth_country_current` or `organization_country`. However, they each have certain problems and limitations.

If you look at the entries in the birth country, you'll see that some countries no longer exist! These include the Soviet Union or Czechoslovakia for example. Hence, using `birth_country_current` is better, since it has the country name which controls the city where the laureate was born. Now, notice that this does not determine the laureates' nationality since some globetrotting folks gave birth to their future Nobel laureate children while abroad. Also, people's nationalities can change as they emigrate and acquire different citizenship or get married and change citizenship. What this boils down to is that we will have to be clear about the assumptions that we will make in the upcoming analysis.

We can create the list of the top 20 countries like this:

```python
1. top_countries = df_data.groupby(['birth_country_current'], 
2.                                   as_index=False).agg({'prize': pd.Series.count})
3.
4. top_countries.sort_values(by='prize', inplace=True)
5. top20_countries = top_countries[-20:]
```

Note that the ranking here determines how our bar chart will be displayed.

```python
1. h_bar = px.bar(x=top20_countries.prize,
2.                y=top20_countries.birth_country_current,
3.                orientation='h',
4.                color=top20_countries.prize,
5.                color_continuous_scale='Viridis',
6.                title='Top 20 Countries by Number of Prizes')
7.
8. h_bar.update_layout(xaxis_title='Number of Prizes', 
9.                     yaxis_title='Country',
10.                     coloraxis_showscale=False)
11. h_bar.show()
```

![[2020-10-20_15-28-14-d0951596c2e1a822e6b53fd9fc21e3ff.png|500]]

The United States has a massive number of prizes by this measure. The UK and Germany are in second and third place respectively.

## Solution 2: Displaying the Data on a Map

To show the above ranking on a color coded map, we need to make use of the ISO codes.

```python
1. df_countries = df_data.groupby(['birth_country_current', 'ISO'], 
2.                                as_index=False).agg({'prize': pd.Series.count})
3. df_countries.sort_values('prize', ascending=False)
```

This means we can use the ISO country codes for the `locations` parameter on the choropleth.

```python
1. world_map = px.choropleth(df_countries,
2.                           locations='ISO',
3.                           color='prize', 
4.                           hover_name='birth_country_current', 
5.                           color_continuous_scale=px.colors.sequential.matter)
6.
7. world_map.update_layout(coloraxis_showscale=True,)
8.
9. world_map.show()
```

I love it how Plotly allows you to zoom in and pan on the map it generates.

![[2020-10-20_15-37-05-1293d524e40e6b3bd08f6f171ab4facb.png|500]]

## Solution 3: The category breakdown by country

Preparing our data to show the breakdown by category and country is challenging. We'll take a two-step approach here. First we count the prizes by category in each country:

```python
1. cat_country = df_data.groupby(['birth_country_current', 'category'], 
2.                                as_index=False).agg({'prize': pd.Series.count})
3. cat_country.sort_values(by='prize', ascending=False, inplace=True)
```

![[2020-10-20_15-39-34-67274118d7ced9c4bf5a8f81c3f667f1.png|500]]

Next, we can merge the DataFrame above with the top20_countries DataFrame that we created previously. That way we get the total number of prizes in a single column too. This is important since we want to control the order for our bar chart.

```python
1. merged_df = pd.merge(cat_country, top20_countries, on='birth_country_current')
2. # change column names
3. merged_df.columns = ['birth_country_current', 'category', 'cat_prize', 'total_prize'] 
4. merged_df.sort_values(by='total_prize', inplace=True)
```

![[2020-10-20_15-42-03-e31d94a8366dcf1b7c91618eb9e234f9.png|500]]

Now we can create our bar chart again. This time we use the color parameter based on the category.

```python
1. cat_cntry_bar = px.bar(x=merged_df.cat_prize,
2.                        y=merged_df.birth_country_current,
3.                        color=merged_df.category,
4.                        orientation='h',
5.                        title='Top 20 Countries by Number of Prizes and Category')
6.
7. cat_cntry_bar.update_layout(xaxis_title='Number of Prizes', 
8.                             yaxis_title='Country')
9. cat_cntry_bar.show()
```

![[2020-10-20_15-44-31-1906cb97c5380befcc9d9c09d2880032.png|500]]

Splitting the country bar chart by category allows us to get a very granular look at the data and answer a whole bunch of questions. For example, we see is that the US has won an incredible proportion of the prizes in the field of Economics. In comparison, Japan and Germany have won very few or no economics prize at all. Also, the US has more prizes in physics or medicine alone than all of France's prizes combined. On the chart, we also see that Germany won more prizes in physics than the UK and that France has won more prizes in peace and literature than Germany, even though Germany has been awarded a higher total number of prizes than France.

![[2020-10-20_15-51-40-5627f6616c19c5a17810133b49a1fbc2 1.png|500]]

When did the United States become so dominant? Was it always this way? Has the prize become more global in scope?

## Solution 4: Country Prizes over Time

To see how the prize was awarded over time. To do that, we can count the number of prizes by country by year.

```python
1. prize_by_year = df_data.groupby(by=['birth_country_current', 'year'], as_index=False).count()
2. prize_by_year = prize_by_year.sort_values('year')[['year', 'birth_country_current', 'prize']]
```

Then we can create a series that has the cumulative sum for the number of prizes won.

```python
1. cumulative_prizes = prize_by_year.groupby(by=['birth_country_current',
2.                                               'year']).sum().groupby(level=[0]).cumsum()
3. cumulative_prizes.reset_index(inplace=True) 
```

Using this, we can create a chart, using the current birth country as the `color`:

```python
1. l_chart = px.line(cumulative_prizes,
2.                   x='year', 
3.                   y='prize',
4.                   color='birth_country_current',
5.                   hover_name='birth_country_current')
6.
7. l_chart.update_layout(xaxis_title='Year',
8.                       yaxis_title='Number of Prizes')
9.
10. l_chart.show()
```

![[2020-10-20_16-05-40-d768858f0f5ab25eb4082e5b2d0332cf.gif|500]]

What we see is that the United States really started to take off after the Second World War which decimated Europe. Prior to that, the Nobel prize was pretty much a European affair. Very few laureates were chosen from other parts of the world. This has changed dramatically in the last 40 years or so. There are many more countries represented today than in the early days. Interestingly we also see that the UK and Germany traded places in the 70s and 90s on the total number of prizes won. Sweden being 5th place pretty consistently over many decades is quite interesting too. Perhaps this reflects a little bit of home bias? 😊