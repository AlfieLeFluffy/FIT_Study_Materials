A matrix is a mathematical construct (notation) that is simplifies the notation of equations. It is used to solve linear equations.
## Types
### Square
Has the same number of rows and columns.
$$
A =
\begin{pmatrix}
2 & 4 & 12 \\
0 & 10 & 5 \\
78 & 5 & 6 \\
\end{pmatrix}
$$
### Zero
A matrix full of zeros.
$$
A =
\begin{pmatrix}
0 & 0 & 0 \\
0 & 0 & 0 \\
0 & 0 & 0 \\
\end{pmatrix}
$$
### Unit
A **square** matrix with the main diagonal with 1s and the rest 0s.
$$
A =
\begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1 \\
\end{pmatrix}
$$
### Step
A matrix with every next rows having one more zero the previous.
$$
A =
\begin{pmatrix}
1 & 1 & 1 \\
0 & 1 & 1 \\
0 & 0 & 1 \\
\end{pmatrix}
$$
### Transposed
A matrix that exchanges rows with columns. If the first one was 2:1 then the new one will be 1:2.
$$
A =
\begin{pmatrix}
3 & 4 & 5 \\
6 & 7 & 8 \\
\end{pmatrix}
;
A^t =
\begin{pmatrix}
3 & 6 \\
4 & 7 \\
5 & 8
\end{pmatrix}
$$
### Symmetrical
A matrix that stays the same even after transposing.
$$
A =
\begin{pmatrix}
3 & 4 & 5 \\
4 & 3 & 6 \\
5 & 6 & 7
\end{pmatrix}
;
A^t =
\begin{pmatrix}
3 & 4 & 5 \\
4 & 3 & 6 \\
5 & 6 & 7
\end{pmatrix}
$$
### Antisymmetric
A matrix that similar to symmetrical, but the elements on the other side are of the inverted value (A = -A). Must have a main diagonal made of **zeros**.
$$
A =
\begin{pmatrix}
0 & -4 & -5 \\
4 & 0 & -6 \\
5 & 6 & 0
\end{pmatrix}
$$
### Diagonal
A matrix that has values only on the main axis and the rest are **zero**.
$$
A =
\begin{pmatrix}
5 & 0 & 0 \\
0 & 7 & 0 \\
0 & 0 & 8
\end{pmatrix}
$$
### Diagonally Dominant
A matrix where the absolute value of each element on the main diagonal is bigger then or equal to the sum of the absolute values of the rest of the elements in either row or column.
$$
A =
\begin{pmatrix}
5 & 0 & 0 \\
0 & 7 & 0 \\
0 & 0 & 8
\end{pmatrix}
$$
### Regular
A matrix of which determinant is **not zero**.
### Positively Defined
A **square** matrix to which applies:
- **x != 0 ⇒ x<sup>T</sup>Mx > 0**
## Determinant
It indicates oriented content, respectively a volume of a 3 row matrix. Some quick ways to judge if the matrix will have a determinant of zero are:
- If the matrix contains a **row of zeros** then the determinant **will be zero**. 
- If the matrix has a **row twice** (duplicates) then the determinant **will be zero**.
Also there are some other things we can consider with the determinant:
- If a matrix **B** would be created by inversing the rows of matrix **A** then their determinants would be **|B| = |-A|**.
- If a matrix **B** would be created by multiplying one row of matrix **A** with a constant **c** then their determinants would be **|B| = c|A|**.
### Cross Rule
When you have a square matrix of 2 or 3 rows you can calculate the determinant using these equations:
$$
A =
\begin{pmatrix}
a & b \\
c & d \\
\end{pmatrix};
D^A = ad - bc
$$

$$
B =
\begin{pmatrix}
a & b & c \\
d & f & g \\
j & k & l
\end{pmatrix};
D^B = afl + bgj + dkc - cfj - bdl - gka
$$
### NxN Determinant
We can divide the matrix into smaller matrixes. For this we can use the Laplace Expansion.
- **Aij = (-1)<sup>i+j</sup> Mij**
With Laplace expansion you choose either a row or a column in which you for each entry in said row or column you cover the opposing column or row and calculate a determinant for the rest of the matrix and multiply it by **(-1)<sup>i+j</sup>**. The sum of these values is the matrixes determinant.