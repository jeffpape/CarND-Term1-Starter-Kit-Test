# [![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/sdc-banner-medium-1170_660.png)](http://www.udacity.com/drive)
# CarND-Term1-Starter-Kit-Test

Files to test the [term 1 starter kit](https://github.com/udacity/CarND-Term1-Starter-Kit) install. 
Run all cells in the jupyter notebook. The notebook should execute all cells with no errors.

------

Since I am new to the computer vision and self driving vehicles spaces, I incorporated the Hough Transform algorithm presented in section 15 of the Finding Lane Lines from the Udacity Self-Driving Car NanoDegree program.

I am in the process of fine tuning the Hough Transform parameters so that my program annotates the lane line markers and not other objects.

Some issues that I encountered using this algorithm are:
1. Defining the capture polygon which tells the algorithm to look for lines is very specific to the images and videos being process. The orientation of the vehicle - really the sensors - to the road and the road’s curvature greatly affect the capture polygon. I created the capture polygon by trial and error by hand. If I was usually this algorithm in its current state for production, I would recommend developing a means to draw by hand possible capture polygons using a tablet; I would create a program that captures the data points of the image as the human traces out the road. The human could do this for several image, then the program would find the small bounding polygon which is the union of all the capture polygons.

2. The weather and daylight conditions greatly effect the brightness and contrast of the pixel data. I can see a place frames where the rapid change from trees’ shadows to bright sunlight washes out the left yellow solid boundary line of the highway. The images and videos are taken under reasonably good weather conditions. I wonder how rain, snow and darkness would affect the images and videos; consequently, you probably should employ a multi-sensory approach such as video cameras, lidar, infra-red.

3. The road material affected the algorithms parameters. I noticed lines appeared where the darker road asphalt color switch to the lighter cement color and then back again. These lines placed additional constraints on the algorithms parameters.

Overall, I found this assignment is really interesting to see how images can be processed to find lane lines programmatically. After some long nights, I am excited to say that my software was able to find some lane lines. I am sure there a much better programs than mine; however this assignment has taught me much how these techniques work.

Thank you,

Jeff Pape

------

Since I am develop on macOS, I used brew to install many of the software packages, such as: ffmpeg.





