# Use HTML Markdown to Make Your Notebook Look Pretty

The cells inside the notebook can either be code cells for your Python code or Text (Markdown) cells. The starter notebook includes a few of these Text cells with section headings and challenge text. However, we can style these cells even more by using HTML (see Days 43 and 44).

## Insert a Markdown Cell

Add a new Text cell below the Introduction.

![[2020-09-25_09-53-23-3145663bff8202a0d6c743347770c287.gif|500]]

## Adding Images

Display an image in a Text cell, use an HTML `<img>` tag with the URL of the image. For example:
```html
1. <img src="https://i.imgur.com/49FNOHj.jpg">
```

If you are using Jupyter Notebook instead of Google Colab, you can also link to one of the files provided in the .zip like so:
```html
1. <img src="assets/bricks.jpg">
```

![[2020-09-25_09-56-39-cc4a596c8ee0a5edf4219832b57f1809.gif|500]]

## Section Headings

You can add section headings using tags like `<h1>` or `<h2>`. However, the Notebook also has its own shorthand for common HTML tags. For example, you can use the `#` symbol as a shortcut. Here's how the headings change their size up to a minimum of `<h5>`:

![[2020-09-25_10-14-15-c15e650ccb641c468c9421a8ffc77a68.gif|500]]

## Challenge

Now, let's get warmed up and write some Python code. Let's find out how many different color LEGO bricks are actually in production!

Read the colors.csv file from the data folder and find the total number of unique colors.

There's a number of different ways you can accomplish this. Maybe try using the [.nunique()](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.nunique.html?highlight=nunique#pandas.DataFrame.nunique) from Pandas this time.

Also, figure out how many of the LEGO colors are transparent compared to how many colors are opaque. See if you can Google your way to finding at least two different ways of arriving at the answer.