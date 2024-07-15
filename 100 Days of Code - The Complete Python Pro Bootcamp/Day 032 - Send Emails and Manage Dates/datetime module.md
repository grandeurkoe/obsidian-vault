# `datetime` module

`datetime` module helps us work with dates.

This can be implemented like this -
```python
import datetime as dt

# datetime.now() function returns todays date and time.
today_datetime = dt.datetime.now()

# You can get specific data from today_datetime like this -
today_month = today_datetime.month
today_day = today_datetime.day
today_date = (today_month, today_day)
```