# [![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/sdc-banner-medium-1170_660.png)](http://www.udacity.com/drive)
# CarND-Term1-Starter-Kit-Test

Files to test the [term 1 starter kit](https://github.com/udacity/CarND-Term1-Starter-Kit) install. 
Run all cells in the jupyter notebook. The notebook should execute all cells with no errors.

------

Since I am new to the computer vision and self driving vehicles spaces, I incorporated the Hough Transform algorithm presented in section 15 of the Finding Lane Lines from the Udacity Self-Driving Car NanoDegree program.

I am in the process of fine tuning the Hough Transform parameters so that my program annotates the lane line markers and not other objects.

My algorithm applies:

0. Transformation from color to gray scale so simplify further processing. 
1. Gaussian smoothing with a kernel size of 5 to smooth any sharp artificial/not important contrast edges.
2. Canny filtering with low threshold of 50 and high threshold of 150 to ignore areas of too much or too little brightness.
3. Polygon to focus on the area of interest - which is the road lanes around the vehicle in the direction of travel.
4. Hough Transformation to detect edges - which are hopefully the lane markers and only the lane markers.
5. Overall the edges detected  - on the original image.


Some issues that I encountered using this algorithm are:

1. Defining the capture polygon which tells the algorithm to look for lines is very specific to the images and videos being process. The orientation of the vehicle - really the sensors - to the road and the road’s curvature greatly affect the capture polygon. I created the capture polygon by trial and error by hand. If I was usually this algorithm in its current state for production, I would recommend developing a means to draw by hand possible capture polygons using a tablet; I would create a program that captures the data points of the image as the human traces out the road. The human could do this for several image, then the program would find the small bounding polygon which is the union of all the capture polygons.

2. The weather and daylight conditions greatly effect the brightness and contrast of the pixel data. I can see a place frames where the rapid change from trees’ shadows to bright sunlight washes out the left yellow solid boundary line of the highway. The images and videos are taken under reasonably good weather conditions. I wonder how rain, snow and darkness would affect the images and videos; consequently, you probably should employ a multi-sensory approach such as video cameras, lidar, infra-red. In addition, the manufacturers can install a weather monitor system in the vehicles. The automatic driving system could potentially read (or obtain over a cellular communication) what the weather conditions are. The system could then use different parameters based on the weather conditions.

3. The road material affected the algorithms parameters. I noticed lines appeared where the darker road asphalt color switch to the lighter cement color and then back again. These lines placed additional constraints on the algorithms parameters.

Overall, I found this assignment is really interesting to see how images can be processed to find lane lines programmatically. After some long nights, I am excited to say that my software was able to find some lane lines. I am sure there a much better programs than mine; however this assignment has taught me much how these techniques work.

4. Vehicles in the other lanes often appeared. I am not exactly sure how to remove these vehicles except by reducing my area of interest by shrinking my polygon of focus. I am undecided if that is the best approach. Yes, the other vehicles are removed, but the area of knowledge is also reduced. Possibly a subsequent step can be added to detect if the edges in the road form vehicles.

Thank you,

Jeff Pape

------

Since I am develop on macOS, I used brew to install many of the software packages, such as: ffmpeg.





