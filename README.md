# LaneLines
Udacity Self Driving Car Nanodegree, Term 1, Project 1

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I extracted a region of interest from the frame, this can be assumed to be a trapezoid shape that tapers in width from bottom to top as due to the perspective effect of the road lines from a distance approaching the camera mounted on the vehicle. The benefit of extracting a region of interest is reducing the overhead of processing on the rest of the pipeline as over half of the image is already disregarded.

Next I extracted segments of the image that matched the color of road lines that we were concerned with. These colors being yellow and white. By using a thresholding function I selected lower and upper bounds in RGB space that white and yellow would lie in. However..

Changing to HLS space..

As a result of thresholding my pipeline outputs two binary images, one of the thresholded white values, the other with the thresholded yellow values. By using the bitwise or operater these two images are fuzed together into one binary image. (Show images of this...)

This binary image can then be run through canny..

This is then run through Hough...

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ...


If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline

Talk about testing at night time..
Talk about testing with a different camera.. evidence, roi..
Curves, and lane crossing

There are a lot of assumptions mentioned above

Reliance on road markings within a particular region

Assuming certain types of lighting conditions due to fixed RGB thresholds for color masking

Lanes must have high contrast with the road so dirt roads would be a problem

Lanes are lines without curves



### 3. Suggest possible improvements to your pipeline

Adaptive region boundaries though camera profiles for different cameras

Adaptive lighting thresholds... investigate

Fit lanes to a polynomial instead of a linear function... curves
