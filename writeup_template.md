# **Finding Lane Lines on the Road** 

## Writeup

---

**Finding Lane Lines on the Road**

The goals of this project are:
* Make a pipeline that finds lane lines in the road in two diferent videos.
* Reflect on your work in a written report


[//]: # (Image References)

---

### Reflection

### 1. Description of the pipeline.

My pipeline consisted of 6 steps:
1.- I converted the images to grayscale.
2.- I performed a Gaussian Smothing.
3.- I apply Canny Edges.
4.- I set a Region of Interest.
5.- I ran a Hough on the edge detected image.
6.- I draw the lines on the original image.

I order to draw a single line on the left and right lanes, I had to modify the draw_lines() function by computing the slope of the raw lines detected; depending on the slope i considered each line as a left line or a right one. Once I separated the lines I computed and Average Slope and "b" for each side, with this slope and b i found my limit points.


[image1]: ./test_images_output/solidWhiteCurve.jpg_Output.jpg "Example of the Algorithm Running"




### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when we get a closed curve; right now I separete left and right lines by positive and/or negative slope, getting a close curve in the road could cause troubles in the algorithm.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to separate right and left lines by their position in the x axis; if their are located to the right of my center are right lines and if they are located to the left of my center they are left lines.
