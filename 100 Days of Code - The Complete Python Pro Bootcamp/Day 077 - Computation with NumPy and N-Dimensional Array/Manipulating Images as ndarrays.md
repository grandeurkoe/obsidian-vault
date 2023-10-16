# Manipulating Images as ndarrays

Images are nothing other than a collection of pixels. And each pixel is nothing other than value for a color. And any color can be represented as a combination of red, green, and blue (RGB).

![[2020-10-12_17-25-44-d5854190572f3330c9e306fbf2933923.gif|500]]

![[2020-10-12_17-19-35-d1bcbb657bc7436583140c99856b1347.png|500]]

You should two import statements at the top. Scipy and PIL will help us work with images.

The `Scipy` library contains an image of a racoon under 'miscellaneous' (misc.). We an fetch it like so:

`1. img = misc.face()`

and display it using Matplotlib's `.imshow()`

![[2020-10-12_17-33-27-9e2e3bb61614dd8f814429f9f7dd6b50.png|500]]

