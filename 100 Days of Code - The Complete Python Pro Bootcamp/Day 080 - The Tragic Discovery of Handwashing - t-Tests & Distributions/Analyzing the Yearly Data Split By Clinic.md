# Analyzing the Yearly Data Split By Clinic

![[2020-10-23_11-22-51-ff500f4a9967079931e0e692b7c45ad3.png|500]]

## Challenge 1: The Yearly Data Split by Clinic

Let's turn our attention to the annual data. Use Plotly to create line charts of the births and deaths of the two different clinics at the Vienna General Hospital.

- Which clinic is bigger or more busy judging by the number of births?
- Has the hospital had more patients over time?
- What was the highest number of deaths recorded in clinic 1 and clinic 2?

## Solution to Challenge 1

To show two line charts side by side we can use Plotly and provide the clinic column as the `color`.

```python
1. line = px.line(df_yearly, 
2.                x='year', 
3.                y='births',
4.                color='clinic',
5.                title='Total Yearly Births by Clinic')
6.
7. line.show()
```

We see that more and more women gave birth at the hospital over the years. Clinic 1, which was staffed by male doctors and medical students was also the busier or simply the larger ward. More births took place in clinic 1 than in clinic 2.

![[2020-10-23_11-31-13-b5897c5011eadac9f54e6956b30d4f97.png|500]]

We also see that, not only were more people born in clinic 1, more people also died in clinic 1.

```python
1. line = px.line(df_yearly, 
2.                x='year', 
3.                y='deaths',
4.                color='clinic',
5.                title='Total Yearly Deaths by Clinic')
6.
7. line.show()
```

![[2020-10-23_11-32-45-1f1c814dd89d9e8102ff7642a53a3ecd.png|500]]

To compare apples and apples, we need to look at the proportion of deaths per clinic.

## Challenge 2: Calculate the Proportion of Deaths at Each Clinic

Calculate the proportion of maternal deaths per clinic. That way we can compare like with like.

- Work out the percentage of deaths for each row in the `df_yearly` DataFrame by adding a column called "`pct_deaths`".
- Calculate the average maternal death rate for clinic 1 and clinic 2 (i.e., the total number of deaths per the total number of births).
- Create another Plotly line chart to see how the percentage varies year over year with the two different clinics.
- Which clinic has a higher proportion of deaths?
- What is the highest monthly death rate in clinic 1 compared to clinic 2?