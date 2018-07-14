# **Finding Lane Lines on the Road** 
---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road

[//]: # (Image References)

[image1]: ./test_images_output/solidWhiteCurve.jpg "solidWhiteCurve"
[image2]: ./test_images_output/solidWhiteRight.jpg "solidWhiteRight"
[image3]: ./test_images_output/solidYellowCurve.jpg "solidYellowCurve"
[image4]: ./test_images_output/solidYellowCurve2.jpg "solidYellowCurve2"
[image5]: ./test_images_output/solidYellowLeft.jpg "solidYellowLeft"
[image6]: ./test_images_output/whiteCarLaneSwitch.jpg "whiteCarLaneSwitch"

---

### Reflection

### 1.Pipeline description

Pipeline consist of the following 5 steps:-
* Converting the images to grayscale -> for better contrast between road and lanes
* Applying Gaussian smoothing -> to reduce noise
* Using Canny Edge Detection -> to detect lane line edges
* Selecting the region of interest for lane detection 
* Applying Hough Tranform line detection 

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by first seperating the left and right detected line from Hough detection , then averaging the lines on each side and finally extrapolating the average to the top and bottom of the lane.

Following are the outputs from the images in test_images folder: 

![alt text][image1]
![alt text][image2]
![alt text][image3]
![alt text][image4]
![alt text][image5]

### 2. potential shortcomings with your current pipeline


* lanes are not properly detected in varying line detection


### 3. possible improvements and future work to your pipeline

* apply HSV or HSL filtering along with yellow and white mask for better detection of lanes in shadows and other such conditions