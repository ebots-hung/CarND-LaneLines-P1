**Finding Lane Lines on the Road**

The main objectives of this project are the following: 

* Implement a pipeline for lanelines finding with pre-built samples. 
* Identify the potential shortcomings/improvements 


[//]: # (Lanelines finding block diagram)

[image1]: ./LanesFinding_Blockdiagram.jpg "Blockdiagram"

---

### Reflection

### 1. Lanelines finding description

Designed pipeline consists of 6 main steps and a final step to merge processed image into original image: 

1. Load/Read test image from samples
2. Grayscale convertion
3. Gaussian Blur for image smoothing
4. Canny transform for edge detection
5. Apply ROI
6. Perform Hough Transform for line detection and draw the whole lane lines
7. Merge lane lines with original image

Algorithm to draw a single line on the lelf and right lanes referred to Greg Yeutter's proposal with minor adaption. 
Here are the basic steps: 
1. Separate the right and left line based on their slope
2. Average the line ending x,y coordinates for each side
3. Calculate the slope and intercept of each average line
4. Using the slope and intercept, extend the lines to the bottom and apex of the lane
5. Update the moving average of the last few lines and the new lines
6. Plot the moving average lines

The output of each step is saved in a directory:

- [test_images_01_grayscale](test_images_01_grayscale)
- [test_images_02_Gaussiansmoothing](test_images_02_Gaussiansmoothing)
- [test_images_03_canny_transform](test_images_03_canny_transform)
- [test_images_04_roi](test_images_04_roi)
- [test_images_05_houghtransform](test_images_05_houghtransform)
- [test_images_06_merge](test_images_06_merge)

- [test_videos_output](test_videos_output)

### 2. Identify potential shortcomings with your current pipeline


* The lanelines detection is not working well to challenge.mp4 video, and laneline drawing function shake when vehicle running over the curved road*

### 3. Suggest possible improvements to your pipeline

* Build up an adaptive algorithm to self-tune the params which helps the pipeline work well with different road's scenarios and draw a curve line for curved road. *

