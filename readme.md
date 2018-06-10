## Finding Lane Lines on the Road ##

### The goal of this project is to create a pipeline that finds lane lines on the road ###

---

### 1. Pipeline description.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I applied Gaussian smoothing and Canny procedure to detect edges.

In order to draw a single line on the left and right lanes, I created the draw_lines() function by averaging line coordinates. Also, I decided to make separate mask for left and right sides.
You can see the [final Jupyter Nonebook with all steps by the link](Finding Lane Lines on the Road.ipynb)
As the result you can see detected lines on the following picture:
![Line detection](examples/laneLines_thirdPass.jpg)


### 2. Potential shortcomings with the current pipeline

The pipeline is unreliable when a car turns left or right and on too bright road segments.

### 3. Possible improvements to your pipeline

A possible improvement would be to replace an average function by weighted average or to take into account X and Y of lines that are closest to the car or make a polynomial (n = 2) regression 

Another potential improvement could be to make two regressions (Y = A*X + B and Y = A*X^2 + B*X + C) and extrapolate lines by one which is the most predictive.