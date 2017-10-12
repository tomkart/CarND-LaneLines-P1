# **Finding Lane Lines on the Road** 

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

[image_canny1]: ./test_images_output/solidWhiteRight_canny.jpg "Canny"
[image_hough1]: ./test_images_output/solidWhiteRight_hough "Hough Transform"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I use Canny edge detector which required gaussian smoothing before hand.  Then I use Hough Transform to find the line with the edge detected image with a mask. Then overlaying the line with the orginal image.

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by calculating the slope (m), but filtering out the lines with slopes which is not our concern.  E.g. Left is m < -0.3, Right is m > 0.3.

Output after Canny:

![alt text][image_canny1]

Output after using Hough Transform on Edge Detected Image

![alt text][image_hough1]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when the line is not in the color white

Another shortcoming could be would be road work with no line marking at all.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to on working all different color of the line.

Another potential improvement could be to smoothing the line motion on the video.
