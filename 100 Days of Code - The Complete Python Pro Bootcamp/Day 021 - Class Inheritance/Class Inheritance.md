# Class Inheritance

Class inheritance allows other classes to inherit attributes and methods of another class.

Class inheritance uses a hierarchical structure.

The class from which we inherit properties are called as Parent class.

The class which inherits properties from other classes are called Child class.

Class inheritance look like this -
```python
class Animal:
	def __init__(self):
		print("I'm an animal.") 
class Fish(Animal):
    def __init__(self):
		super().__init__()
```

Here `super()` refers to the Animal class. It will initialize everything that the super class can do in the Fish class.