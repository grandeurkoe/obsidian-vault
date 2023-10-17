# Use scikit-learn to Run Your Own Regression

Let's dive into our linear regression model a bit more. We are using a **univariate** regression. This is a regression with a single **explanatory variable** (our movie BUDGET). Explanatory variables are also referred to as **features** in machine learning terminology.

Using our data on budgets, the linear regression estimates the best possible line to fit our movie revenues. The regression line has the following structure:

![[2020-10-16_15-19-24-b9cd86771c12cda554da251a16471df9.png|500]]

To find the best possible line, our regression will estimate the y-intercept ("theta zero") and the slope ("theta one"). The line's **intercept** on the y-axis tells us how much revenue a movie would make if the budget was 0. The **slope** tells us how much extra revenue we get for a $1 increase in the movie budget.

![[2020-10-16_15-31-02-3bdbeb669ce3d7ecebe72abb986e8d35.png|500]]

So how can we find out what our model's estimates are for theta-one and theta-zero? And how can we run our own regression, regardless of whether we want to visualise it on a chart? For that, we can use [scikit-learn](https://scikit-learn.org/stable/).

![[2020-10-16_15-32-56-3a64b2f8f6ba4fb460c26d3d4573bbb8.png]]

