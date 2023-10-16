# Manipulating Images as ndarrays

Images are nothing other than a collection of pixels. And each pixel is nothing other than value for a color. And any color can be represented as a combination of red, green, and blue (RGB).

![[2020-10-12_17-25-44-d5854190572f3330c9e306fbf2933923.gif|500]]

![[2020-10-12_17-19-35-d1bcbb657bc7436583140c99856b1347.png|500]]

You should two import statements at the top. Scipy and PIL will help us work with images.

The `Scipy` library contains an image of a racoon under 'miscellaneous' (misc.). We an fetch it like so:

`1. img = misc.face()`

and display it using Matplotlib's `.imshow()`

![[2020-10-12_17-33-27-9e2e3bb61614dd8f814429f9f7dd6b50.png|500]]

## Challenge

What is the data type of `img`? Also, what is the shape of `img` and how many dimensions does it have? What is the resolution of the image?

## Solution: An image as a ndarray

Let us question the nature of our reality and take a look under the surface. Here's what our **"image"** actually looks like:

![[2020-10-13_09-28-44-6f41078c913d2304ad5e606add8704e2.png|500]]

We can now clearly see that we're dealing with a ndarray. And it's a 3 dimensional array at that.

![[2020-10-12_17-42-09-192012f781f92f80a849dc1ea3212494.png|500]]

There are three matrices stacked on top of each other - one for the red values, one for the green values and one for the blue values. Each matrix has a 768 rows and 1024 columns, which makes sense since 768x1024 is the resolution of the image.

## Challenge

Now can you try and convert the image to black and white? All you need need to do is use a [formula](https://en.wikipedia.org/wiki/Grayscale#Colorimetric_(perceptual_luminance-preserving)_conversion_to_grayscale).

![](https://img-c.udemycdn.com/redactor/raw/2020-10-12_17-56-16-aff5999394e88abae2995c6d700a8cb1.png)

`Y_linear` is what we're after - our black and white image. However, this formula only works if our red, green and blue values are between 0 and 1 - namely in sRGB format. Currently the values in our `img` range from 0 to 255. So:

- Divide all the values by 255 to convert them to sRGB.
- Multiply the sRGB array by the `grey_vals` array (provided) to convert the image to grayscale.
- Finally use Matplotlib's [`.imshow()`](https://matplotlib.org/3.1.1/api/_as_gen/matplotlib.pyplot.imshow.html) with the colormap parameter set to gray `cmap=gray` to display the result.

## Solution: Converting an image to grayscale

The first step is a division by a scalar

`1. sRGB_array = img / 255`

Here NumPy will use broadcasting to divide all the values in our ndarray by 255.

Next, we use matrix multiplication to multiply our two ndarrays together.

`1. grey_vals = np.array([0.2126, 0.7152, 0.0722])`

These are the values given by the formula above

`1. img_gray = sRGB_array @ grey_vals`

We can either multiply them together with the @ operator or the `.matmul()` function.

`1. img_gray = sRGB_array @ grey_vals`

`1. img_gray = np.matmul(sRGB_array, grey_vals)`

Finally, to show the image we use Matplotlib

`1. plt.imshow(img_gray, cmap='gray')`

The `cmap` parameter is important here. If we leave it out the function will not know that is dealing with a black and white image.

![[2020-10-12_18-03-51-46b947197834216ff69717fd4ac7dd58.png|500]]

## Challenge

Can you manipulate the images by doing some operations on the underlying ndarrays? See if you can change the values in the ndarray so that:

You flip the grayscale image upside down like so:

![[2020-10-13_09-48-42-6da00043154d3fd57f2b979b692125c1.png|500]]
Rotate the color image:

![[2020-10-13_09-48-48-618965070981a8096f73de791f750b21.png|500]]

Invert (i.e., solarize) the colour image. To do this you need to convert all the pixels to their "opposite" value, so black (0) becomes white (255).

![[2020-10-13_09-48-54-e30020abc219020c9a4c214cc55a6da1.png|500]]

