# Road Lane Line detection using OPEN CV
Lane line detection is a critical component for self-driving cars because detection of lanes in a road is an important factor for automatic cars to move the car in their respective lanes to avoid accidents.

:pushpin:**Existing System :**

Some existing technologies utilize some kind of sensor such as Lidar, Radar, and vision sensors. In which, Lidar and radar are only used for obstacle detection, unique vision sensors are used for lane detection and vehicle detection.

:pushpin:**Disadvantages of Existing System :**
* There is an increase in autonomous vehicles and these vehicles do not have proper guidance leading to accidents. 
* Most existing lane line detection algorithms are mainly designed for structured roads, due to the influence of the surrounding environment of the road, such as the influence of shadows of surrounding trees or buildings and the pair of vehicles ahead of the road. 

:pushpin:**Proposed System :**
* The proposed system utilizes road lane detection algorithm for road lane identification. This is to helps the autonomous vehicles to identify the road lanes.
* The techniques used to detect mathematical shapes like this is called Hough Transform Hough Transform can detect shapes like circles, rectangles, triangles and lines.

:pushpin:**Advantages of Proposed System:**
* The proposed system utilizes road lane detection algorithm for road lane identification. This is to helps the autonomous vehicles to identify the road lanes.
* The techniques used to detect mathematical shapes like this is called Hough Transform Hough Transform can detect shapes like circles, rectangles, triangles and lines.

:page_with_curl:**Flowchart :**

![image](https://user-images.githubusercontent.com/67002556/194056345-926f6970-b539-48aa-867c-7d3971a40565.png)

:pushpin:**Detailed Explanation of Each Step :**

   ***1. Input Video :***
   * Input of Video is read and the video is a combination of frames so now we are discussing here the processing of the single frame i.e., image here.
   
   ![image](https://user-images.githubusercontent.com/67002556/194053367-f1ea5fa3-55d7-45a0-b579-c4e9c840522b.png)
 
   ***2 .Gray Scale Conversion :***
   * Converts the Image from three channel image (RGB Image) to single channel image(Gray Scale Image).
   *  A grayscale (or gray level) image is simply one in which the only colors are shades of gray. The reason for differentiating such images from any other sort of color image is that less information needs to be provided for each pixel. In fact a ‘gray’ color is one in which the red, green and blue components all have equal intensity in RGB space, and so it is only necessary to specify a single intensity value for each pixel, as opposed to the three intensities needed to specify each pixel in a full color image.
   
   ![image](https://user-images.githubusercontent.com/67002556/194053450-7823da88-ce3b-466b-a746-92adb6d0323c.png)

   ***3. Gaussian Filter :***
   * It is used to reduce the noise of an image and smoothen the image. We use this to remove many detected edges and keep most prominent edges.
   * It is applied because it is important to catch as many edges as possible in the image. Noise in the images may create false edges and ultimately effect the edge detection.

   ![image](https://user-images.githubusercontent.com/67002556/194053504-65d2dbec-9546-4fbc-b0bb-7c439a1f7590.png)

   ***4. Canny Edge Detection :***
   * Canny edge detection is an operator that uses the horizontal and vertical gradients of the pixel values of an image to detect edges.
   * Canny edge detection is a technique to extract useful structural information from different vision objects and reduce the amount of data to be processed.
   * Canny method identifies edges in our image that an edge corresponds to our region where there is sharp change in intensity between adjacent pixels of an image
   * General criteria of edge detection is, an edge in the image should only be marked once and detection of edges with low error rate, which means that detection should accurately catch as many edges in the image possible. 
 
  ![image](https://user-images.githubusercontent.com/67002556/194056233-b61a5280-d667-42ed-a2c0-2dfb2478ac59.png)

   ***5.Masking :***
   * Masking is an image processing method in which we define a small image piece and use it to modify a larger image.
   * In masking, polygon region is made to obtain the region of interest in the canny image.
   * The region of interest for the car’s camera is only the two lanes immediately in it’s field of view. We can filter out the extraneous pixels by using a polygon region of interest and removing all other pixels that are not in the polygon region.

   **Mask**

   ![image](https://user-images.githubusercontent.com/67002556/194054150-da5e6d19-22af-439a-adcc-d5675db38c1a.png)

   ![image](https://user-images.githubusercontent.com/67002556/194054189-bc57ff61-d4e7-46eb-b018-eaafda7169f2.png)

   **Region of Interest**

   ![image](https://user-images.githubusercontent.com/67002556/194054645-8a75e915-0492-4d62-8b8a-8107590c81c6.png)

   ***6.Hough Transoform :***
   * The Hough transformation converts a “x vs y” line to a point in “gradient vs intercept(m-c)” space. Points in the image will correspond to lines in hough space. An intersection of lines in hough space will thus correspond to a line in Cartesian space. Using this technique, we can find lines from the pixel outputs of the canny edge detection output.
   * The main advantage of the Hough transform technique is that it is tolerant of gaps in feature boundary descriptions and is relatively unaffected by image noise.

   ![image](https://user-images.githubusercontent.com/67002556/194054920-cf57baf3-4c38-4d6e-a463-06c082a1f52b.png)

   ***7.Extrapolating the Lines :***
   * Now, we construct the left lane and right lane. We do this by separating the small lines into two groups, one with a positive gradient and the other with a negative gradient. Due to the depth of the camera’s view, the lane lines slant towards each other as we go further in depth, so that should have the opposite gradients. We then take the average gradient and intercept values for each group and construct our global lane lines from there. 
   * The lane lines are then extrapolated to the edge detected pixel with the minimum y-axis coordinate and the pixel with the maximum y-axis coordinate.

   ![image](https://user-images.githubusercontent.com/67002556/194055211-cc2bc29d-6cdd-45a4-a33e-ece554c541c4.png)

   ***8.Add the extrapolated lines to the input image :***
   * The line obtained after extrapolating, then the lines is overlayed to the input image.
   * We do this by weight value to the original image based on the detected line coordinates of the image that consists of only Lanes.

   ![image](https://user-images.githubusercontent.com/67002556/194055469-f08230aa-b804-47a8-928c-b350a7d668cd.png)
   
:pushpin:**Conclusion :**
* Autonomous Driving Car is one of the most disruptive innovations. One of the many steps involved during the training of an autonomous driving car is lane detection, which is the preliminary step. Lane detection is one of the most challenging tasks. A vision system using on-board camera looking outwards from the windshield is presented here. The system acquires the front view using a camera mounted on the vehicle and detects the lanes by applying few processes. The system was investigated under various situations of changing illumination, and shadows effects in various road types without speed limits. The system has demonstrated a robust performance for detecting the road lanes under different conditions.














