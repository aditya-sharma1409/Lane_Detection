# Lane Detection
Lane detection is crucial for Advanced Driver Assistance Systems (ADAS) and autonomous vehicles. 
This project aims to is to utilize the Hough Transform to accurately identify and highlight lane boundaries in the input video stream. 
This provides a foundation for applications such as ADAS and autonomous vehicles.

# Methodology
In this project, we adopt the following methodology to accurately detect and highlight lanes using only image processing techniques, without incorporating machine learning:

**Capturing and Decoding Video File:**

* Capture the video using the VideoFileClip object.
* Initialize video capture and decode each video frame into a sequence of images.

**Grayscale Conversion of Image:**

* Convert RGB video frames to grayscale to expedite processing, as a single-channel image is faster to process than a three-channel colored image.

**Noise Reduction:**

* Noise can create false edges, so image smoothing is essential.
Use Gaussian blur for noise reduction. Gaussian blur, a typical image filtering technique, lowers noise and enhances image characteristics by applying a weighted average considering surrounding pixels.

**Canny Edge Detector:**

* Compute gradient in all directions of the blurred image and trace edges with significant intensity changes.

**Region of Interest:**

* Focus only on the region covered by the road lane by creating a mask of the same dimension as the road image.
* Perform a bitwise AND operation between each pixel of the canny image and the mask, masking the canny image to show the region of interest traced by the polygonal contour of the mask.

**Hough Line Transform:**

* Use the Hough transformation, a feature extraction method, to find basic geometric objects like lines.
* Convert the picture space into a parameter space to identify shapes by accumulating voting points.
* Employ the probabilistic Hough Line Transform to address computational complexity, speeding up processing while preserving accuracy by applying the transformation to a randomly selected subset of points.

**Draw Lines on the Image or Video:**

* After identifying lane lines in the region of interest using the Hough Line Transform, overlay them on the visual input (video stream or image).

This methodology ensures robust and accurate lane detection, contributing to the safety and efficiency of ADAS and autonomous vehicle systems.

# Future Scope
