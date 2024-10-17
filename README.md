# Image-manipulation with python library 
Let do some basic stuff! .. Using numpy library lets perform image manipulation 
## Overview 
Using python libraries - numpy, matplotlib.pyplot we are going to take a random image and perform some array operation on it. 
since we are using a image it will have pixel in it, so converting into numpy array will change it into rows, columns and depth 
depth in images are generally a colour grade (R,G,B) its like a 3D matrix. 
## Tools 
Google collab 

## Content
1.Opening an image

2.Details of an image

3.Visualise RGB channels

4.Rotate an image

5.Reverse an image

6.Crop/Trim an image

7.Blurr an image

8.Image Contrast

# Opening an image 
How can we open an image in our code?

To open an image, 

we will use the matplotlib library to read and show images.

We will cover all the functionalities of matplotlib in detail in visualization lecture.

For this use case, just know that it uses an image module for working with images.
It offers two useful methods imread() and imshow().

imread() – to read the images

imshow() – to display the images

```sql
!gdown 17tYTDPBU5hpby9t0kGd7w_-zBsbY7sEd
img = np.array(plt.imread('fruits.png'))
plt.imshow(img)
```
# Details of an image
We can see the dimension and shape of this image, using the Image.ndim and Image.shape properties
```sql
print('# of dims: ',img.ndim) # dimension of an image
print('img shape: ',img.shape) # shape of an image
```
1 . Coloured images have a 3rd dimension for depth or RGB colour channel.
2. Here, the depth is 3.
3. But we will come to what RGB colour channels are in a bit.

# Visualise RGB channels
These are values of each pixel of an image.

Each pixel is made up of 3 components/channels - Red, Green, Blue - which form RGB values.

Coloured images are usually stored as 3-dimensional arrays of 8-bit unsigned integers.

So, the range of values that each channel of a pixel can take is  0  to  28−1 .

That is, each pixel's each channel, R, G and B can range from 0 to 255.

```sql
img_green = img
img_green[:,:,(0,2)]=0
plt.imshow(img_green)
img_red  = img
img_red[:,:,(1,2)] = 0
plt.imshow(img_red)
img_blue = img
img_blue[:,:,(0,1)]=0
plt.imshow(img_blue)
```

# Rotating an Image
What if we want to rotate the image?
Remember image is a Numpy array.
Rotating the image means transposing the array.
For this, we'll use the np.transpose() function in numpy.


Now, let's understand np.transpose() function first
It takes 2 arguments.
1st argument is obviously the array that we want to transpose (image array in our case).
2nd argument is axes
Its a tuple or list of ints.
It contains a permutation of [0,1,..,N-1] where N is the number of axes of array.


Now, our image array has 3 axes (3 dimensions) ---> 0th, 1st and 2nd
We specify how we want to transpose the array by giving an order of these axes inside the tuple.

Vertical axis (Row axis) is 0th axis
Horizontal axis (Column axis) is 1st axis
Depth axis is 2nd axis
In order to rotate the image, we want to transpose the array.

That is, we want to transpose rows into columns and columns into rows.

So, we want to interchange the order of row and column axis ---> interchange order of 0th and 1st axis.

We don't want to change the depth axis (2nd axis) ---> So, it will remain at its original order position.

Now, the order of axes in orginal image is (0, 1, 2).

What will be the order of axes rotated image or transposed array?
The order of axes in rotated image will be (1, 0, 2).
Order (Position) of 0th and 1st column is interchanged.
```sql
import numpy as np 
import matplotlib.pyplot as plt 
jonny = np.array(plt.imread('golden.jpeg'))
jonny_rotate = np.transpose(jonny,(1,0,2))
plt.imshow(jonny_rotate)
```





