# Type Checking and Type Conversion

## Type Checking

You can check the data type of any variable using the `type()` function.

Call to the `type()` function look like this -
```python
# argument is the variable whose type you want to check.
type(argument)
```

##  Type Conversion

Type conversion involves converting a variable from one data type to another.

For example, the input() function always returns a string. So, even if you entered an integer as an input it still returns a string. Thus converting this string back to integer becomes vital.

The following function can be used to convert a variable from one data type to another -

1. `float(argument)`  - Converts whatever argument is passed to it into a floating point number.
2. `int(argument)` - Converts whatever argument is passed to it into an integer.
3. `str(argument)` - Converts whatever argument is passed to it into a string.