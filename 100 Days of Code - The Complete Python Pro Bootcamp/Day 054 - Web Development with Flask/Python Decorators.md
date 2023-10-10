# Python Decorators

A decorator function is a function that gives additional functionalities to an existing function.

Functions are first class objects i.e. they can be passed as arguments in a function.

A decorator function is a function that wraps another function and gives it additional functionalities.
```python
# Python Decorator Function
import time
def delay_decorator(function):
	def wrapper_function():
		time.sleep(2)
		# Do something before calling the function.
		function()
		function()
		# Do something after calling the function.
	return wrapper_function

# Functions with @delay_decorator before them will be delayed by 2 seconds.
# @delay_decorator is what we call Syntactic sugar.

@delay_decorator
def say_hello():
	print("Hello")

@delay_decorator
def say_bye():
	print("Bye")

def say_greeting():
	print("How are you?")

say_hello()
# OR
decorated_function = delay_decorator(say_greeting)
decorated_function()
```