---
tags:
  - ZPO
aliases:
  - motion analysis
  - motion tracking
  - motion extraction
sources:
  - "[[ZPO_11_Motion_Analysis.pdf]]"
---
Motion analysis is used to extract new information about motion or space from a sequence of images or video.
## Problems
Some of the typical problems that motion analysis has to solve are:
- Illumination changes
- Aperture problem
- In differential methods
- Changes not caused by the object movement
- Shadows
## Methods
Some of the main method are:
### Differential
This method uses the difference of consecutive frames to estimate the changes and motion. It is a rather simple and fast calculation but it is also very sensitive to noise, slight movements, etc. It is usually supplemented by further processing or blob detection. Changing the lighting has a significant effect on the result and the reference image must be updated.
Some of the basic addition can be thresholding, erosion, opening and closing from [[Morphology|morphology]].
### Local Binary Patterns
The image is split into segments and through several operations the LBP histogram for each segment is created. Motion detection is done through comparing histogram of actual and reference (previous) frames. The image can split into overlapping regions, which leads to a better localization precision.
This is a fast method that can be easily implemented in HW. It is invariant to pixel intensity transformations in the image. Stable against minor camera shakes. Quite inaccurate location of changes and only detect changes and not direction.
### Background Modeling
This method is based on the segmentation of the foreground from the background. Simple models of the background, such as average frame or reference frame, are not good enough for this task. Something like **Gaussian Mixture Model** (GMM) is used instead, which is a linear combination of Gaussian functions.
Each image pixel is modelled by around 3-5 Gaussian functions. Expectation maximization is a method fitting the Gaussian functions to data distribution.
### Optical Flow
This method uses the apparent motion of brightness patterns in the image. Motion field describes the movement of 3D objects projected to 2D images -  vectors of movements.
This is sensitive to window size, lighting changes, shadows, etc. In general optical flows corresponds to the motion field, but some it has some issues, often with optical illusions such as the barber's pole, which rotates horizontally, but due to the way the stripes are painted it appears to be traveling upwards.
Some ways to create an optical flow field are:
- Differential methods
	- Image derivations
	- Horn-Schunck
	- Lucas-Kanade
- Matching methods
	- Detection and tracking of specific structures (features)
#### Lucas-Kanade
This method uses an iterative approach and the difference between two images to estimate the optical flow. The basic estimation idea is:
1. The image $I(x,y,t)$ is shifted according to the optical flow obtained so far.
2. Estimation of the residual motion $df$ for a "shifted" image and $I(x,y,t+1)$, which creates relation $f'=f+df$
3. Repeat until threshold met or other condition satisfied.
#### Sparse Flow
A feature-based motion estimation that extracts visual features (key points, corners, blobs) from the initial image and then uses a matching approach with Sum of Squared Differences to match/find the features in the next image.
This is the most robust motion tracking method, especially for movement in the pixel range up to tens of pixels.
### Advanced Methods
Some of the more advanced methods are:
- Kalman filters
- Particle filters
	- The state (position) of an object is modeled by a set of particles with assigned weights
	- Importance sampling step
	- Selection step