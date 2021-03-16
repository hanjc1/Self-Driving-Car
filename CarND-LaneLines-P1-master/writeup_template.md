# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 6 steps. First, I converted the images to grayscale, then I utilized the gaussian function to make the image blur. I used canny function for edge detection. Region masking function was used, and then hough line function ws used. 

In order to draw a single line on the left and right lanes, I modified the draw_lines() function. I first divded the image into two sides, left and right using "img.shape[1]/2". Each segments of lines have its own x and y postion. I used the "np.polyfit" to return polynomial coefficients, in this case, the coefficients are "m" and "b". After I found minimun and maximum values for both left and right sections of image. Since x, m ,and b are defined, using "y= mx + b" to find "y". Since there are minimum and maximum points are on the each right and left sides of the image, I connected two points to create a line. 


![alt text][image1]

My pipeline consisted of 
### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be curve lane since the equation we are using is for linear.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to using non-linear equation. For the curve lane, it would be better using 3rd degree or higher polynoimal function.