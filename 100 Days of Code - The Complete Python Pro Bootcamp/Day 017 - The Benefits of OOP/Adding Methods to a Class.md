# [Adding Methods to a Class](Python%20Syntax%20Cheat%20Sheet.pdf#page=15)

You can create class methods like this -
```python
class Car:
def enter_race_mode(self) : 
	self.seats = 2
```

You can call class methods like this -
```python
toyoto = Car()
toyoto.enter_race_model()
print(toyoto.seats)
```