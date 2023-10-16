# NumPy's ndarray - Incredible Power at Your Fingertips!

Let’s import NumPy

![[2020-10-12_09-41-31-067a30d8e9bda1db2f2e5752632a0da3.png|500]]

We’ll follow convention and use the name `np`.

The crown jewel of NumPy is the `ndarray`. The **ndarray** is a _homogeneous n-dimensional array_ object. What does that mean? 🤨

A Python List or a Pandas DataFrame can contain a mix of strings, numbers, or objects (i.e., a mix of different types). **Homogenous** means all the data have to have the same data type, for example all floating-point numbers.

And **n-dimensional** means that we can work with everything from a single column (1-dimensional) to the matrix (2-dimensional) to a bunch of matrices stacked on top of each other (n-dimensional).

![[2020-10-12_15-34-45-6fdebf22c1ab4c51fd82687144c0f215.gif|500]]

## 1-Dimension

Let’s create a 1-dimensional array (i.e., a “vector”)

`1. my_array = np.array([1.1, 9.2, 8.1, 4.7])`

We can see `my_array` is 1 dimensional by looking at its shape

`1. my_array.shape`

We access an element in a ndarray similar to how we work with a Python List, namely by that element's index:

`1. my_array[2]`

Let’s check the dimensions of `my_array` with the `ndim` attribute:

`1. my_array.ndim`

![[2020-10-12_09-45-49-516f9f87a63a881bad1f7d13a190b2a5.png|500]]

## 2-Dimension

