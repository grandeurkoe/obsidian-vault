# API Parameters

API Parameters allow you to give an input to an API.

You can create API Parameters as a dictionary -
```python
parameter = {
   'lat': MY_LAT,
   'lng': MY_LNG,
  }
```

You can pass these parameter to the API -
```python
response = requests.get(url="https://api.sunrise-sunset.org/json", params=parameter)
```