#What is computer Vision and how to start with it?
Computer vision is a machine learning field whose goal is to help computers **see**. its end goal is to make intelligent systems which can understand digital images.
The best way to start with Computer Vision is using the open source computer vision library (**OpenCV**), so 

## What is OpenCV?
OpenCV is a huge open-source library for computer vision, machine learning, and image processing. it can be used to process images and videos to identify objects, faces, or even the handwriting of a human.

## How to use OpenCV?
it is supporting programming languages like C++ and python, so here we will use python to explain how to use it.

## Install OpenCV
You can install OpenCV by using the pip command 
```bash
$ pip install opencv-python
```

## Reading Image
Given an image, to load it in, we can use the OpenCV function **imread**. the image can be displayed using the function **imshow**
```py
image_var = cv.imread('file-path')
cv.imshow('image_name', image_var)
```

## Resizing images
Images read in might not be of the correct size or might not fit the screen correctly. To overcome this, we can resize the image.
```py
cv.resize(image, new dimensions, interpolation)
```

## Drawing
We can draw images in OpenCV. OpenCV allows us to draw various images such as rectangles, circles, lines and even put text ober our image.

## Basic Image Functions
OpenCV has inbuilt functions which allow us to perform various operations on our images such as blurring, resizing, cascading/edge detection, cropping.

### Blurring
Blurring is a method used to remove noise from an image by applying a low pass filter over an image. We smooth out the edges and make the transition from one color to another very smooth.

## Image Transformation
We can transform the image we have read in various ways including traslation, i.e shifting it along x or y axis, rotation, flipping and cropping.

## Contour Detection
A contour is a curve or line joining all points which have the same color or intensity. Contours help us find the points which lie on the same plane and assist in edge detection.

## Split image Color Channels
Any image is basically a combination of three main colours **Res**, **Green**. **Blue** (RGB). OpenCV allows us to split our image into its respective color channels.

## Bitwise operation on images
BITWISE operations are operators such as AND, OR, XOR etc. in image processing, they are used to create a new image or for masking. the operation is done between each pixel of two images.

## Edge Detection
Edge detection is used to find the boundaries of an image by finding inconsistencies in brightness. it is used for image segmentation and data extraction.

## Reading Videos
```py
capture = cv.VideoCapture('dof.mp4')

while True:
    isTrue, frame = capture.read()

    if not isTrue:
        break

    cv.imshow('Video', frame)

    if cv.waitKey(20) & 0xFF==ord('d'):
        break

capture.release()
```