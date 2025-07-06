Equations, where as the variables are inputted **derivations of the functions**. For some we can find direct analytical solution, but commonly this is **not possible and is too complicated**. Thankfully the solution of differential equations can be rather well approximated using some of the **numeric methods** that use [[Iterative Solving of Algebraic Equations|iterative]] approach.
## Types
- **One-Step**: Bases calculation only on the current step (the current evaluation). This is for example **Euler's Method**, **Runge-Kutta** methods (**RK2**, **RK4**, **RK8**)
- **Multi-Step**: Bases calculation not only on the current step, but also on the history of states (evaluations of previous steps). These methods can be quicker the one-step, but they usually struggle at the start. For some amount of steps **n** the system uses only one-step methods. This can be for example **Adams-Bashforth Method**.
- **Predictor-Collector**: The method first calculates the approximation for **y<sub>i+1</sub>**. After that in that point if calculates a derivation **f<sub>i+1</sub>**, which is used to then calculate a more precise approximation of **y<sub>i+1</sub>**. 
- **Explicit**: The outcome of each iteration must be evaluated by **substituting into the formula**. 
- **Implicit**: The outcome requires solving of **algebraic equations** for each iteration.
## Methods
### Euler's Method
The simplest method for numeric approximation. The method first calculates the tangent line at a point, which is given by the first [[Derivation]] of the function in that point. the tangent line says how much the y value increases/decreases when x changes (this defines a straight line).
#### Steps
- $y' = f(x,y)$
- $y(x_{0}) = y_{0}$
- $y_{i+1} = y_{i} + h \times f(x_{i},y_{i})$
- $i = 1, 2, \dots$
### Runge-Kutta
One-Step numeric method that expands on the Euler's methods. RK methods use different orders. Coefficients for these methods are calculated in a way so that a method of oder **b** would match up with [[Derivation#Taylor's Polynom|Taylor's Polynom]] of function **y(t)** of the same order. For calculations we commonly use **Runge-Kutta** of the **4th order**. For RK method of **k order** we would calculate **k** approximations (the second relies on the first, the third relies on the second, ...) and the final approximation is calculated as a step multiplied by their weighted average.
#### Steps
- $y_{n+1} = y_{n} + h \times \left( \frac{1}{2}k_{1} + \frac{1}{2}k_{2} \right)$
- $k_{1} = f(t_{n},y_{n})$
- $k_{2} = f(t_{n+h},y_{n+hk_{1}})$
### Adams-Bashforth
A **Multi-Step** method that remember previous states and uses them in its calculations.
#### Steps
- $y_{n+2} = y_{n+1} +\frac{3}{2}h \times f(t_{n+1},y_{n+1}) - \frac{1}{2}h \times f(t_{n},y_{t})$
## Tough Systems
Tough system are systems of equations that are through for common **numeric methods** to crack. There can be issues with the step not being able to be shortened which results in rounding errors and such. For these it is necessary to use different special methods.
## Errors of Numeric Methods
We can divide error in numeric method into:
- **Local Errors** get created in each step such as rounding errors and approximation errors.
- **Accumulative Errors** get created by combining local errors over time.