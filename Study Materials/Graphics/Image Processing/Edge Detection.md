---
tags:
  - ZPO
aliases:
  - edge detection
  - edging... hehehe
---
For edge detection we can use several methods.
## Properties
Some of the properties that edge detection methods can have (qualities) are:
- Resilience against blur/noise
- Localization
- Size of the response
## Gradient
An edge within the image technically is a sharp change in intensity. This is not usually a one pixel wide changes and affects surrounding pixel creating a gradient from both sides of the edge. This change can be described by its size $|G|$ and its direction $\phi$. This a function of one pixel and its surroundings. 
## Image Derivation
The first derivation of an image can be created by using the kernels:
$$\frac{1}{8}\times
\begin{matrix}
 0 & 0 & 0 \\
-1 & 1 & 0 \\
 0 & 0 & 0
\end{matrix}
\ ; \ \ \ \ \
\frac{1}{8}\times
\begin{matrix}
 0 & -1 & 0 \\
 0 &  1 & 0 \\
 0 &  0 & 0
\end{matrix}
$$
To detect the direction of the edge created by the first derivation we must use a set of kernels that correspond with several directions. These kernels can be for example:
- Sobel
- Kirsch
- Robinson
- Prewitt
## Methods
Some of the most common methods for edge detection are:
### Sobel
This method uses what is called Sobel operators, which are convolution kernels with the shape:
$$\frac{1}{8}\times
\begin{matrix}
-1 & 0 & 1 \\
-2 & 0 & 2 \\
-1 & 0 & 1
\end{matrix}
\ ; \ \ \ \ \
\frac{1}{8}\times
\begin{matrix}
-1 & -2 & -1 \\
0  & 0  & 2 \\
1  & 2  & 1
\end{matrix}
$$
The Sobel edge detection pipeline is:
1. Gaussian blur of the image
2. Application of the Sobel operators
3. Thresholding
Important thing to keep in mind that the Sobel operators are the first derivations of a Gaussian blur kernel by x and y. The second derivation of the Gaussian blur is the Laplacian, which detects intersection with zero.
### Canny Detector
This algorithm in such a way as to satisfy the properties as much as possible. The pipeline is:
1. Gaussian blur
2. First derivation
3. Non-maxima suppression
4. Thresholding with hysterias
For the first derivation the operator used are the first derivation of the Gaussian blur kernel in the direction x and y. The non-maxima suppression is done by suppressing values along the gradient that are not the maximum. The last step is thresholding with hysterias. This kind of thresholding uses two values: low and high, where in order for something to count as 1 there must be an unbroken path from the given pixel to at least one pixel with the high value and the pixel must not be of a low value. The path is broken by low values.
### Laplacian Function
The Laplacian transformation (second derivative) of a Gauss function/kernel. The edge detection is done by detecting a intersection with a zero value (finding a zero value), which is easier then finding extremes. The major disadvantages are that the image is smoothed way too much, sharp corner disappear and has a tendence to create closed loops of edges.
The Laplacian operator is invariant to rotation (does not detect orientation, isotropic).
### Marr and Hildreth Edge Operator
This method, sometimes it is also known as a Mexican hat, uses the Laplacian operator and several other steps, which are:
1. Convolution of image and Laplacian Gauss operator.
2. Detection of zero values
It is very stable and robust method for detecting changes in an image and localization of zeros in the places of edges. It has issues with false edges and not exactly precise localization of edges.
### Difference of Gaussian
This method is an approximation of the Laplacian Gauss operator by using two Gaussian filters. The first filter has sigma $0.3$ and the second $1.0$, they are both the same size and both centered. By filtering the image by both filters and then subtracting the second result from the first we can a rough estimation of what the Laplacian operator would create. In some ways this behaves like a bandwidth gate/filter.
A major advantage of this is that both Gaussian filters are separable and the calculations can be run in parallel.
By running multiple layers of these calculations over different scale we can get several results that all highlight edges in slightly different ways and resolution.
### Hough's Transformation
This method uses the parametric representation of lines/circles/etc. The points within the original image are transformed into the parametric space based on the currently extracted shape. For example if we are extracting lines then the parameters can be the distance of the lines from the space origin $p$ and the angle on under which the line around the space origin $\phi$.
Maximum (convergence) points within the parametric space represent the parameters of all lines found within the image.
A brute force method for transforming points for line extraction into the parametric space is:
1. Plot a number of lines going through the point, all with different parameters (like distance and angles).
2. Extract the parameters of each line. This can done by creating a perpendicular line to the extracted line that intersects the space origin and takings its length and angle.
3. After extracting all lines, compare the results and find the the parameters with the most similar values. For example with if within the result there exists a repeating entries of extracted lines with the same distance and angle from the space origin then it most likely the sought after result.
Similar things can be done with circle, where the extracted features can be their center position and radius (or for simplification if we know the radius then just the center position). The parametric space can technically have as many dimensions as we want and we can extract as many parameters as we want, but usually it is best to simplify to as little parameters as we need.
### Active Contours
This method, also known as Snakes, uses a lines that update their position/contour based on external forces, trying to find a curve with the least/minimum energy. This method usually involves manual initialization for the best results.
### Histogram of Oriented Gradients
Uses weighted gradients to estimate edges.
### Scale Invariant Feature Transform
This method, also known as SIFT, uses features/shape extraction and image gradients on different scales to extract objects/edges from an image.