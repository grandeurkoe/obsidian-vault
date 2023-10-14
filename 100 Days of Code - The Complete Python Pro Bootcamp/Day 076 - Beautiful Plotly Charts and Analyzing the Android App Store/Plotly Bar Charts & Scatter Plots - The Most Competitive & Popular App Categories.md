# Plotly Bar Charts & Scatter Plots: The Most Competitive & Popular App Categories

If you were to release an app, would you choose to go after a competitive category with many other apps? Or would you target a popular category with a high number of downloads? Or perhaps you can target a category which is both popular but also one where the downloads are spread out among many different apps. That way, even if it’s more difficult to discover among all the other apps, your app has a better chance of getting installed, right? Let’s analyze this with bar charts and scatter plots and figure out which categories are dominating the market.

We can find the number of different categories like so:

`1. df_apps_clean.Category.nunique()`

Which shows us that we there are 33 unique categories.

To calculate the number of apps per category we can use our old friend `.value_counts()`