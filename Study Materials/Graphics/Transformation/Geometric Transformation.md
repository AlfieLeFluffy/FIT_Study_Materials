Geometric transformation changes the positions of points (peaks) of objects v current coordinate system or changes the coordinate system.
## Linear Transformation
Linear transformation keeps the linear combinations of objects (vectors can be applied in any order and the outcome will be the same). For any two vectors and a scalar we can say that:
- f(x<sub>1</sub> + x<sub>2</sub>) = f(x<sub>1</sub>) + f(x<sub>2</sub>)
- f(a * x<sub>1</sub>) = a * f(x<sub>1</sub>)
Amongst these transformations we have change in **scale** (enlargement, reduction), **rotation** and **skewing**.
## Affine Transformation
Affine transformation keeps the kolinearity and division ration of objects (point that lay on a line will still lay on a line even after transformation). All basic geometric transformations such as **scale Sc**, **rotation R**, **skewing Sh** and **translation T** are affine transformations. They can be described as linear transformations followed up by shifting.
## Homogeneous (Weighted) Transformation
To the standard **Cartesian** coordinates such as x, y in 2D space and x, y, z in 3D space we add another variable (coordinate) **w**. In affine transformation this variable would always be **w = 1**. This variable allows the work with all basic transformation separately with the help of [[Matrix]] **notation**. Matrix notation allows for easy composition of transformations.
### Translation T
Both in 2D and 3D space this operation is done by rewriting the lowest row with the desired translation operations.
- To move an object from \[x, y, 1\] to \[x', y', 1\] by **dx** and **dy** we can use the matrix:
$$
[x',y',1] = [x,y,1]\times
\begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
dx & dy & 1 \\
\end{pmatrix}
$$

- To reverse the move we can use the matrix with negative numbers:
$$
[x,y,1] = [x',y',1]\times
\begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
-dx & -dy & 1 \\

\end{pmatrix}
$$
### Scale Sc
To change a scale of an object you write the desired changes onto the axis of the matrix.
- To scale an object from \[x, y, 1\] to \[x', y', 1\] by **dx** and **dy** we can use the matrix:
$$
[x',y',1] = [x,y,1]\times
\begin{pmatrix}
dx & 0 & 0 \\
0 & dy & 0 \\
0 & 0 & 1 \\
\end{pmatrix}
$$
- To reverse the scale we can use the matrix with scale numbers inverted:
$$
[x,y,1] = [x',y',1]\times
\begin{pmatrix}
\frac{1}{dx} & 0 & 0 \\
0 & \frac{1}{dy} & 0 \\
0 & 0 & 1 \\
\end{pmatrix}
$$
### Skew Sh
To change a skew of an object you write the desired changes onto the opposite axis of the matrix. We disregard the last column/row.
- To skew an object from \[x, y, 1\] to \[x', y', 1\] by **dx** and **dy** we can use the matrix:
$$
[x',y',1] = [x,y,1]\times
\begin{pmatrix}
1 & dx & 0 \\
dy & 1 & 0 \\
0 & 0 & 1 \\
\end{pmatrix}
$$
- To reverse the skew we can use the matrix with the negative skew numbers:
$$
[x,y,1] = [x',y',1]\times
\begin{pmatrix}
1 & -dx & 0 \\
-dy & 1 & 0 \\
0 & 0 & 1 \\
\end{pmatrix}
$$
To skew objects in 3D we use different style of matrix:
$$
Shyz =
\begin{pmatrix}
1 & Shy & Shz & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 1 & 0 \\
0 & 0 & 0 & 1
\end{pmatrix}
Rhxz =
\begin{pmatrix}
1 & 0 & 0 & 0 \\
Shx & 1 & Shz & 0 \\
0 & 0 & 1 & 0 \\
0 & 0 & 0 & 1
\end{pmatrix}
Rhxy =
\begin{pmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
Shx & Shy & 1 & 0 \\
0 & 0 & 0 & 1
\end{pmatrix}
$$
### Rotation R
To change the rotation of an object we need to use goniometric functions.
- To rotate an object from \[x, y, 1\] to \[x', y', 1\] by **a** degrees we can use the matrix in one direction:
$$
[x',y',1] = [x,y,1]\times
\begin{pmatrix}
\cos a & \sin a & 0 \\
-\sin a & \cos a & 0 \\
0 & 0 & 1 \\
\end{pmatrix}
$$
- And in the other:
$$
[x',y',1] = [x,y,1]\times
\begin{pmatrix}
\cos a & -\sin a & 0 \\
\sin a & \cos a & 0 \\
0 & 0 & 1 \\
\end{pmatrix}
$$
For 3D objects these matrixes are different:
$$
Rx =
\begin{pmatrix}
1 & 0 & 0 & 0 \\
0 & \cos a & \sin a & 0 \\
0 & -\sin a & \cos a & 0 \\
0 & 0 & 0 & 1
\end{pmatrix}
Ry =
\begin{pmatrix}
\cos a & 0 & \sin a & 0 \\
0 & 1 & 0 & 0 \\
-\sin a & 0 & \cos a & 0 \\
0 & 0 & 0 & 1
\end{pmatrix}
Rz =
\begin{pmatrix}
\cos a & \sin a & 0 & 0 \\
-\sin a & \cos a & 0 & 0 \\
0 & 0 & 1 & 0 \\
0 & 0 & 0 & 1
\end{pmatrix}
$$
## Composing Transformations
When composing transformations in Homogenous system the order in which we combine them matters. For example if we translate, rotate and scale an object, it would look differently from scaling, translating and rotating and object. This also depends on if the point description is done as a row or as a column:
- **Point is in a row**: For the new point P' the point P must come first. $$P' = P \times T \times R \times S$$ 
- **Point is in a column**: For the new point P' the point P must come last. $$P' = T \times R \times S \times P$$
In both case thought the sequence of **transformations keep their order** of first transformation going first and so on.