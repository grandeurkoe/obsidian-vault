# Python Typing - Type Hints and Arrows

Instead of assigning a variable with a value, you can also declare a variable as a data type.
```python
age: int
```

If you don't want to assign a value to a variable at present but would like to assign it a value at a later time then you can use Type Hints.

You can also use Type Hints for functions like this -
```python
def police_check(age: int):
	if age > 18:
		can_drive = true
	else:
		can_drive = false
	return can_drive
```

You can also specify the data type of the output returned by the function.

You can do so by using the Arrow (->).

So the Arrow in the above code can be implemented as -
```python
def police_check(age: int) -> bool:
	if age > 18:
		can_drive = true
	else:
		can_drive = false
	return can_drive
```