# `strftime()` function

 The strftime() function allows us to format the date that we get from [[datetime module]] into any format that we want.
```python
import datetime as dt
datetime_today = dt.datetime.now()
date_today = datetime_today.date()
# OR
from datetime import datetime
date_today = datetime(year=2023, month=9, day=7)
date_format = date_today.strftime("%Y%m%d")
# This will format the date from YYYY-MM-DD to YYYYMMDD
```