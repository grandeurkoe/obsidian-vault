# `*args` - Many Positional Arguments

Using `*args `you can provide an unlimited number of positional arguments.

`*args` can be implemented like this - 
```python
def add(*args):  
	for n in args:  
		print(n)  
	add(3,4,5,6)
```

You don't have to write args. It can be anything like `*add`.

Here `*args` is a tuple.