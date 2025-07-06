These methods lead to a solution of a matrix in a **finite amount of steps**. This solution should be **accurate** if we do not do not make any rounding errors.
## Crammers Rule
A great method for solving a small set of equations. These equations should be **regular** as this method uses determinants. To calculate a variable in the matrix we replace its column with the results of the system.
$$
x_{1} = \frac{D_{1}}{D};
x_{2} = \frac{D_{2}}{D};
x_{3} = \frac{D_{3}}{D};
$$
So as an example we can do solve this:
$$
x + y = 3;
x - 2y = 1
$$
$$
A =
\begin{pmatrix}
1 & 1 \\
1 & -2 \\
\end{pmatrix};
D_{A} = 1 \times -2 - 1 \times 1 = -3
$$
$$
A_{1} =
\begin{pmatrix}
3 & 1 \\
1 & -2 \\
\end{pmatrix};
D_{1} = 3 \times -2 - 1 \times 1 = -7;
$$
$$
A_{2} =
\begin{pmatrix}
1 & 3 \\
1 & 1 \\
\end{pmatrix};
D_{2} = 1 \times 1 - 3 \times 1 = -2;
$$
$$
x_{1} = \frac{-7}{-3} = \frac{7}{3};
x_{2} = \frac{-2}{-3} = \frac{2}{3}
$$
## Gaussian Elimination Method
The basic idea of the method is to rework the matrix into a [[Matrix#Step|Step Matrix]]. This can done either through **switching around of rows**, **multiplication or division of rows through a non zero value** or **addition or subtraction of rows between each other**. If we ignore rounding errors then this method returns a correct result, but it is computationally quite difficult. It is necessary to do around n<sup>3</sup> operations, or cubic difficulty.
$$
\begin{pmatrix}
2 & 3 & 7 & | & 47 \\
3 & 8 & 1 & | & 50 \\
0 & 3 & 3 & | & 27 \\
\end{pmatrix}
$$
$$
\begin{pmatrix}
2 & 3 & 7 & | & 47| &  \times 3\\ 
3 & 8 & 1 & | & 50| &  \times 2 \\
0 & 3 & 3 & | & 27 \\
\end{pmatrix}
$$
$$
\begin{pmatrix}
6 & 9 & 21 & | & 141 & | & row_{2}- row_{1} \\ 
2 & 16 & 3 & | & 100 \\
0 & 3 & 3 & | & 27 \\
\end{pmatrix}
$$
$$
\begin{pmatrix}
6 & 9 & 21 & | & 141 \\ 
0 & 7 & -19 & | & -41  & | & \times 3\\
0 & 3 & 3 & | & 27  & | & \times 7\\
\end{pmatrix}
$$
$$
\begin{pmatrix}
6 & 9 & 21 & | & 141 \\ 
0 & 21 & -57 & | & -132 & | & row_{3}-row_{2}\\
0 & 21 & 21 & | & 189 \\
\end{pmatrix}
$$
$$
\begin{pmatrix}
6 & 9 & 21 & | & 141 \\ 
0 & 21 & -57 & | & -132 \\
0 & 0 & 78 & | & 312 \\
\end{pmatrix}
$$
The equations come out as:
$$
6x_{1} + 9x_{2} + 21x_{3} = 141
$$
$$
21x_{2} - 57x_{3} = -123
$$
$$
78x_{3} = 312
$$
$$
x_{1}=4;
x_{2}=5;
x_{3}=2
$$
## LU Decomposition
This method solves a matrix through decomposition through a [[Matrix#Unit|Unit Matrix]]. The LU refers to Lower-Upper as the outcome will be product of two matrixes, both of which are a [[Matrix#Step|Step Matrixes]], but on the opposing sides of the main axis. While using LU decomposition you cannot switch rows during the method. The method otherwise works like a **Gaussian Elimination**, but all of the steps are recorded in another matrix, which is the unit matrix.