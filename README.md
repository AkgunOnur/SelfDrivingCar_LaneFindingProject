# **Finding Lane Lines on the Road** 

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road for both images and video stream

---

### Overview

In this project, it is aimed to find lane lines on the road to find region of motion for a self driving car.

### 1. Steps of the project

Pipeline has 5 steps. 
-Image is converted into grayscale mode
-Grayscale image is blurred by using Gaussian filter
-Canny Edge Detector is used to find edges
-Region of interest mask is applied to image 
-Probabilistic Hough Line Transform is used to detect lines

Let's see every step of the algorithm

[//]: # (Image References)

[image1]: ./examples/1.png "Grayscale image"
[image2]: ./examples/2.png "Blurred image"
[image3]: ./examples/3.png "Canny Edge Detector"
[image4]: ./examples/4.png "Region of interest"
[image5]: ./examples/5.png "Hugh Line Transform"

The image which has RGB channels is converted into grayscale mode which has one channel

![alt text][image1]

In this part, image is blurred with a 5x5 kernel

![alt text][image2]

In the use of Canny Edge Detector, low and high thresholds are defined to find edges which correspond lane lines in this work

![alt text][image3]

Region of interest, which keeps only a particular region and sets zero the rest of the image, is defined to avoid false detections

![alt text][image4]

Edge points are found by Canny Edge Detector above. It is also needed to combine those points to construct a lane line by using Probabilistic Hugh Line Transform

![alt text][image5]


### 2. Potential shortcomings


One potential shortcoming would be that the algorithm is sensitive to noise which means that anything which has same color with lanes or adjacent to lane line might be considered as part of lane. Therefore, there might be little deviations in finding lane lines.

Another shortcoming could be finding the region of interest. The view of a car might be different than the previous. Thus, there might be a problem in generalization of the algorithm for every car.


### 3. Possible improvements

A possible improvement would be to take advantage of deep neural networks to improve the algorithm. Especially, it might be needed to make the algorithm less sensitive to noise and more flexible on determining the region of interest.
