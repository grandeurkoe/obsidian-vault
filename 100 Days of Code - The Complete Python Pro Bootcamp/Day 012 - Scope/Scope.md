# Scope

Python doesn't have block scope.

## Global Variable

You can modify global variable like this - 
```python
global_variable = value
def function() :
	# Introduce global variable global_variable to function(). 
	global global_variable 
```

Avoid modifying global variable within a local function.

## Global Constants

Global constants are variables whose value you don't want to change throughout the program.

Declaring a global constants look something like this -
```python
# Write PI in uppercase.
PI = 3.14159 
```

Declare the global constant with capital letters.