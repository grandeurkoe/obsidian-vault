# `**kwargs` - Many Keyword Arguments

Using `**kwargs` you can provide an unlimited number of keyword arguments.

Here `**kwargs` is a dictionary.

`**kwargs` can be implemented like this -
```python
class Car:  
	def __init__(self, **kw):   
		# If the user doesn't provide kw["make"] then the get() function will  
		# set that value as None.  
		self.make = kw.get("make")  
		self.model = kw.get("model")  
car = Car(make="Nissan")
```