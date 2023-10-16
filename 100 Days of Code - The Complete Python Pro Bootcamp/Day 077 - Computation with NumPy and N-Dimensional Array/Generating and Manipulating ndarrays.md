# Generating and Manipulating ndarrays

NumPy has many _many_ pages of documentation on all of its extensive functionality. But rather than go through the list one by one, the best way to actually learn NumPy is to apply it to a series of small problems. That way you can familiarize yourself with how to use NumPy for the common use cases that you'll encounter on your own data science journey too.

## Challenge 1

Use [`.arange()`](https://numpy.org/devdocs/reference/generated/numpy.arange.html)to create a vector `a` with values ranging from 10 to 29. You should get this:

`print(a)`

`[10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29]`

## Challenge 2

Use Python slicing techniques on `a` to:

- Create an array containing only the last 3 values of `a`
- Create a subset with only the 4th, 5th, and 6th values
- Create a subset of `a` containing all the values except for the first 12 (i.e., `[22, 23, 24, 25, 26, 27, 28, 29]`)
- Create a subset that only contains the even numbers (i.e, every second number)

## Challenge 3

Reverse the order of the values in `a`, so that the first element comes last:

`[29, 28, 27, 26, 25, 24, 23, 22, 21, 20, 19, 18, 17, 16, 15, 14, 13, 12, 11, 10]`

If you need a hint, you can check out this part of the [NumPy beginner's guide](https://numpy.org/devdocs/user/absolute_beginners.html#how-to-reverse-an-array)

## Challenge 4

Print out all the indices of the non-zero elements in this array: [6,0,9,0,0,5,0]

## Challenge 5

Use NumPy to generate a 3x3x3 array with random numbers

Hint: Use the [`.random()` function](https://numpy.org/doc/stable/reference/random/index.html?highlight=random#module-numpy.random)

## Challenge 6

Use [`.linspace()`](https://numpy.org/doc/stable/reference/generated/numpy.linspace.html) to create a vector `x` of size 9 with values spaced out evenly between 0 to 100 (both included).

## Challenge 7

Use [`.linspace()`](https://numpy.org/doc/stable/reference/generated/numpy.linspace.html) to create another vector `y` of size 9 with values between -3 to 3 (both included). Then plot `x` and `y` on a line chart using Matplotlib.

## Challenge 8

Use NumPy to generate an array called `noise` with shape 128x128x3 that has random values. Then use Matplotlib’s [`.imshow()`](https://matplotlib.org/3.1.1/api/_as_gen/matplotlib.pyplot.imshow.html) to display the array as an image.

The random values will be interpreted as the RGB colors for each pixel.