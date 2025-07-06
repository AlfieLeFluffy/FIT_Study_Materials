Unlike [[Direct Solving of Algebraic Equations]] these methods do not lead to a definitive result in a finite amount of steps. We start with an approximation of the solution and then each step we refine this approximation, bringing it closer to the solution. These methods approach the solution incrementally and when the evaluation is precise enough we can end the method.
## Jacobi Method
The method converges if the system of equations is [[Matrix#Diagonally Dominant|Sharply Rows Diagonally Dominant]] (the sum of the absolute values of the row is bigger then the value on the diagonal) or [[Matrix#Diagonally Dominant|Sharply Column Diagonally Dominant]] (the sum of the absolute values of the column is bigger then the value on the diagonal).  If these conditions are not met then the method will can converge, but does not have to.
### Steps
- $x^{(r+1)}_{1} = \frac{1}{a_{1,1}} \times (a_{1,4}  + x^{(r)}_{2} + x^{(r)}_{3})$
- $x^{(r+1)}_{2} = \frac{1}{a_{2,2}} \times (a_{2,4}  + x^{(r)}_{1} + x^{(r)}_{3})$
- $x^{(r+1)}_{3} = \frac{1}{a_{3,3}} \times (a_{3,4}  + x^{(r)}_{1} + x^{(r)}_{2})$
## Gauss-Seidel Method
The method is similar to **Jacobi method**, but it differs in that each step uses the new variable from the previous equation. The same conditions for convergence apply and also converges if it is positively defined. This can done through a **subdeterminants of the upper left corner** (all must be positive) or the **pivot test** (converting the matrix into upper triangle matrix and checking if values on the diagonal are greater then 0).
### Steps
- $x^{(r+1)}_{1} = \frac{1}{a_{1,1}} \times (a_{1,4}  + x^{(r)}_{2} + x^{(r)}_{3})$
- $x^{(r+1)}_{2} = \frac{1}{a_{2,2}} \times (a_{2,4}  + x^{(r+1)}_{1} + x^{(r)}_{3})$
- $x^{(r+1)}_{3} = \frac{1}{a_{3,3}} \times (a_{3,4}  + x^{(r+1)}_{1} + x^{(r+1)}_{2})$