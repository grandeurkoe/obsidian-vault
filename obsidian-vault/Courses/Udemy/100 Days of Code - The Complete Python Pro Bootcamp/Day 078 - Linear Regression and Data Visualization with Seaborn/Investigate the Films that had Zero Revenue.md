# Investigate the Films that had Zero Revenue

Now that we've done some legwork on cleaning our data, we can investigate our data set more thoroughly.

## Challenge 1

1. What is the average production budget of the films in the data set?
2. What is the average worldwide gross revenue of films?
3. What were the minimums for worldwide and domestic revenue?
4. Are the bottom 25% of films actually profitable or do they lose money?
5. What are the highest production budget and highest worldwide gross revenue of any film?
6. How much revenue did the lowest and highest budget films make?

## Challenge 2

How many films grossed $0 domestically (i.e., in the United States)? What were the highest budget films that grossed nothing?

## Challenge 3

How many films grossed $0 worldwide? What are the highest budget films that had no revenue internationally (i.e., the biggest flops)?


## Solution 1

We can answer many of the questions with a single command: `.describe()`.

![[2020-10-14_17-25-22-50638b2907fc1a16098f440072858223.png|500]]

The average film costs about $31m to make and makes around 3x that (or ~$89m) in worldwide revenue. So that's encouraging.

But quite a lot of films lose money too. In fact, all the films in the bottom quartile lose money, since the average cost is $5 million and they only bring in $3.8m in worldwide revenue!

The minimum domestic and worldwide revenue is $0. That makes sense. If a film never gets screened or is cancelled, then this is the number we would expect to see here.

On the other hand, the highest production budget was $425,000,000 and the highest worldwide revenue was $2,783,918,982. $2.7 Billion revenue! Holy smokes.

So which film was the lowest budget film in the dataset?

![[2020-10-14_17-28-28-0e643636fa2dfc616b2624c049e3be3e.png|500]]

I've ... never heard of this film. But it looks like a real money maker. It grossed $181,041 with a measly $1,100 budget. 😮 Wow. Talk about return on investment!

![[2020-10-14_17-31-29-814c8fa514cdd86e226534cd68167830.png|500]]

And the highest budget film in the dataset is:

![[2020-10-14_17-35-51-45a833f04cef1a441bdc004a84391593.png|500]]

Sigh, I remember watching this film in the cinema with 3D glasses 🤓 and not wanting the film to ever end! I would have been quite content living with those blue people. 😊

## Solution 2

We see that there are 512 films in the dataset that had no revenue in the United States. However, the highest budget films with no revenue have a release date AFTER the date on which the dataset was compiled (May 1st, 2018).

```python
1. zero_domestic = data[data.USD_Domestic_Gross == 0]
2. print(f'Number of films that grossed $0 domestically {len(zero_domestic)}')
3. zero_domestic.sort_values('USD_Production_Budget', ascending=False)
```

## Solution 3

When we check worldwide revenue instead, we see that there are 357 films that made no money internationally. Once again, some of the films have not been released yet at the time the data was compiled. However, 512 versus 357. Why is there a difference? 

The reason some international films were never screened in the United States.  In fact, we can see an example of this in our previous screenshot. "Don Gato, el inicio de la pandilla" made about $4.5 million dollars in the box office, but nothing in the United States. Perhaps they should have screened it there too, considering it cost $80 million to make!

```python
1. zero_worldwide = data[data.USD_Worldwide_Gross == 0]
2. print(f'Number of films that grossed $0 worldwide {len(zero_worldwide)}')
3. zero_worldwide.sort_values('USD_Production_Budget', ascending=False)
```

![[2020-10-14_17-49-17-c0c42e8a463d6d79a09dadfe670a1b07.png|500]]