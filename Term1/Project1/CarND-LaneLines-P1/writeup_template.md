# **Finding Lane Lines on the Road**

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 7 steps.
1) Use color thresholds and mask the image with colors outside the thresholds
2) Use region thresholds and mask the rest of the area outside the region
3) Grayscale the image
4) Use Gaussian blurring on the image
4) Use Canny edge detection to mark the edges
5) Use Hough transform to find the lines
6) Draw the lines using draw_lines()

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by
1) Calculating the slope to separate positive and negative slope lines
2) Putting slope thresholds
3) Checking that both starting and end point of a line lie in the same half of the image
4) Drawing the line
5) Creating extra points on the line and saving them (using length of the line as weightage for that line)
6) Creating lines for both sides and using their slope and intercept to extrapolate to images bottom to the region of interest  


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when the color difference between the lane and road is very less.

Another shortcoming could be if the turn is very sharp


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to use the slope of lane line from last few frames with higher weightage to the more recent one and decreasing to the older ones   

Another potential improvement could be to putting better thresholds for region of interest
