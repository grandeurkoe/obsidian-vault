# Dynamic Typing

You can change the data type of  a variable by changing its contents. This is known as Dynamic Typing.

For instance,
```python
a = 2
```

Here `a` is of `int` data type.

Now, if I assign `a = "string"`. Then a would be of `str` data type.

Python is unique in that it will remember that `a` is of `str` data type.

If you try to perform an operation like this -
```python
a = a ** 2
```

Then this will generate a TypeError.