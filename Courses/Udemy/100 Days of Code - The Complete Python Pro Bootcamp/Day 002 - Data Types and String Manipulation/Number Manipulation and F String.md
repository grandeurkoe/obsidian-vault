# Number Manipulation and F String

## Number Manipulation

`round(argument)` - Rounds off the argument(i.e., floating point number) to the nearest integer.

`round(mathematical operation, precision)` - Performs mathematical operation. Rounds of the results of the mathematical operation to the specified precision.

`n1 // n2` - Here // is floor division. Divided n1 by n2. If the result is a floating point number then it converts it into an integer by removing the numbers after the decimal point.

Shorthand notation -

1. a += 2 -> a = a + 2
2. a -= 2 -> a = a - 2
3. a *= 2 -> a = a * 2
4. a /= 2 -> a = a / 2

## F String


If I want to print the value of a variable onto the console using the print() function, the code will look something like this :
```python
N1 = 1
N2 = 2
print(N1 + " is odd." + N2 + " is even.")
```

The above code clearly shows how tedious writing a `print()` function could be if there were more variables.

F String allows us to integrate code into our `print()` function.

`print()` function for above code using F String would look something like this :
```python
print(f"{N1} is odd. {N2} is even.")
```