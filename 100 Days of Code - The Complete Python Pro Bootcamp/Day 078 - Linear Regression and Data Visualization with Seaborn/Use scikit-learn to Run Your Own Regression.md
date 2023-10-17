# Use scikit-learn to Run Your Own Regression

Let's dive into our linear regression model a bit more. We are using a **univariate** regression. This is a regression with a single **explanatory variable** (our movie BUDGET). Explanatory variables are also referred to as **features** in machine learning terminology.

Using our data on budgets, the linear regression estimates the best possible line to fit our movie revenues. The regression line has the following structure:

![[2020-10-16_15-19-24-b9cd86771c12cda554da251a16471df9.png|500]]

To find the best possible line, our regression will estimate the y-intercept ("theta zero") and the slope ("theta one"). The line's **intercept** on the y-axis tells us how much revenue a movie would make if the budget was 0. The **slope** tells us how much extra revenue we get for a $1 increase in the movie budget.

![[2020-10-16_15-31-02-3bdbeb669ce3d7ecebe72abb986e8d35.png|500]]

So how can we find out what our model's estimates are for theta-one and theta-zero? And how can we run our own regression, regardless of whether we want to visualise it on a chart? For that, we can use [scikit-learn](https://scikit-learn.org/stable/).

![[2020-10-16_15-32-56-3a64b2f8f6ba4fb460c26d3d4573bbb8.png]]

## Import scikit-learn

Let's add the `LinearRegression` from scikit-learn to our notebook.

![[2020-10-16_15-35-31-9dd5b42978718c28394b328f636862ae.png|500]]

Now we can run a [LinearRegression](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LinearRegression.html). First, let's create a `LinearRegression` object that will do the work for us.

`1. regression = LinearRegression()`

Now we should specify our features and our targets (i.e., our response variable). You will often see the features named capital `X` and the target named lower case `y`:

```python
1. # Explanatory Variable(s) or Feature(s)
2. X = pd.DataFrame(new_films, columns=['USD_Production_Budget'])
3.
4. # Response Variable or Target
5. y = pd.DataFrame(new_films, columns=['USD_Worldwide_Gross']) 
```

Our `LinearRegression` does not like receiving Pandas Series (e.g., `new_films.USD_Production_Budget`), so I've created some new DataFrame here.

Now it's time to get to work and run the calculations:

```python
1. # Find the best-fit line
2. regression.fit(X, y)
```

That's it. Now we can look at the values of theta-one and theta-zero from the equation above.

![[2020-10-16_16-11-16-2c2283cc96442b3c62e1c95e9eb31cde.png|500]]

Both `intercept_` and `coef_` are simply [attributes of the LinearRegression object](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LinearRegression.html). Don't worry about the underscores at the end, these are simply part of the attribute names that the scikit-learn developers have chosen.

How do we interpret the y-intercept? Literally, means that if a movie budget is $0, the estimated movie revenue is -$8.65 million. Hmm... so this is clearly unrealistic. Why would our model tell us such nonsense? Well, the reason is that we are specifying what the model should be ahead of time - namely a straight line - and then finding the best straight line for our data. Considering that you can't have negative revenue or a negative budget, we have to be careful about interpreting our very simple model too literally. After all, it's just an estimate and this estimate will be the most accurate on the chart where we have the most data points (rather than at the extreme left or right).

What about the slope? The slope tells us that for every extra $1 in the budget, movie revenue increases by $3.1. So, that's pretty interesting. That means the higher our budget, the higher our estimated revenue. If budgets are all that matter to make lots of money, then studio executives and film financiers should try and produce the biggest films possible, right? Maybe that's exactly why we've seen a massive increase in budgets over the past 30 years.