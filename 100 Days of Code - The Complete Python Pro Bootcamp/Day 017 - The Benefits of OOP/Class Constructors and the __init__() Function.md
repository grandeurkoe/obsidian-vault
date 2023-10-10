# Class Constructors and the `__init__()` Function

If you want to initialize the attributes during the creation of an object. Then you have to use the `_ _ init_ _()` function.

You can define the class constructor like this -
```python
def __init__(self) :
	# initialize attributes
```

The `__init__()` function will be called every time an object is created.

`self` is the actual object being initialized.

To pass attributes during the construction of the object the code looks something like this -
```python
def __init__(self, seats)
self.seats = seats
```

You need to pass the arguments to the __init__(self, seats) function during the creation of an object. You can do so like this -
```python
my_car = Car(5)
```