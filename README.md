# LaneLines
Udacity Self Driving Car Nanodegree, Term 1, Project 1

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I extracted a region of interest from the frame, this can be assumed to be a trapezoid shape that tapers in width from bottom to top as due to the perspective effect of the road lines from a distance approaching the camera mounted on the vehicle. The benefit of extracting a region of interest is reducing the overhead of processing on the rest of the pipeline as over half of the image is already disregarded.

Next I extracted segments of the image that matched the color of road lines that we were concerned with. These colors being yellow and white. By using a thresholding function I selected lower and upper bounds in RGB space that white and yellow would lie in. However..

Changing to HLS space..


In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ...


If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
