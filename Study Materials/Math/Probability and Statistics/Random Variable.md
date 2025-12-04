---
tags:
  - IPT
  - MSP
aliases:
  - random variable
---
Random variable is a numeric evaluation of a random experiment (that we can numerically evaluate). A **random variable** is signified by **upper-case letters X, Y, Z**. Their probability is noted with **lower-case letters x, y, z, p**.
The probability of a random **variables X** gains value of **x** is noted as:
$$
P(X = x)
$$
And similarly we can interpret:
$$
P(X > x); P(X < x)
$$
We differentiate between:
- **Discrete** variables
- **Continuous** variables
### Distribution Function
Describes **division** (behaviour) of **random variables**. It is **non-decreasing** and from the **right continuous** function. Distribution function **F(x)** of a random variable **X** assigns each real number **x** probability that the random variable **X** will be evaluated as **lesser then or equal to x**.
$$
F(x) = P(X \leq x)
$$
With a **discrete random variable** the function will be a step function.
#### Properties
- **0 <= F(x) <=1**
- **F(x)** is non-decreasing and from the right continuous function.
- **lim(x->-inf) F(x) = 0**, **lim(x->inf) F(x) = 1**
- **P( a < X <= b) = F(b) - F(a)** for each **a, b ∈ R, a < b**
- **P(X = x) = F(x) - lim(t->x-)F(t)**
- F has a finite amount of points of discontinuity.
### Probability Density Function
Set (describes) **probability distribution of a random variable** (with a discrete random variable it can be expressed in a way that each probability **P(x)** is evaluated and for each x of domain of definition of the variable **X**). We notate it with a lower case letter **f(x)** and it can be obtained be the **first derivation of the distribution function F'(x) = f(x)**.
#### Properties
- $f(x) \geq 0$
- $f(x) = \frac{dF(x)}{dx}$
- $\int_{-\infty}^{\infty} fx \, dx = 1$
- $P(a \leq X \leq b) = \int_{a}^{b} f(x) \, dx$
### Random Variable Characteristics
#### Mean Value E(X)
The mean value of a **discrete random variable** is a **weighted average of all of its possible values**. 
$$
E(X) = \sum_{x} xp(x)
$$
For continuous function it is the sum is replaced with an **integral**.
$$
E(X) = \int_{M} xf(x) \ dx
$$
Other properties are:
- $E(a) = a$
- $E(aX +b)  = aE(X) + b$
- $E(X \pm Y) = E(X) \pm E(Y)$
#### Dispersion D(X)
Also the **mean quadratic dispersion** is a characteristic of the variability of the distribution of the random variable. It describes the variability of a distribution of a set of random values ​​around its mean value. It is the the sum of **areas of squares** of each value by their **distance from the mean value**.
$$
D(X) = E(X^2) - [E(X)]^2
$$
$$
E(X^2) = \sum x^x \times p(x)
$$
#### Standard Deviation (σ(X))
The standard deviation show how **each case differs from each other** in the set of tested values. It is calculated as a the **square root of Dispersion**.
$$
σ(X) = \sqrt{ D(X) }
$$