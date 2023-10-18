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