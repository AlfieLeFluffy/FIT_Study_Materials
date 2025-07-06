## Terminology
### Basic Space
**Ω** is the set of all possible values that a **random value X** can become and is also called the **basic space**. A basic space for sequential coin tosses looks like **Ω = {(heads, heads), (heads, tails), (tails, heads), (tails, tails)}**.
### Random Phenomenon
Is any subset of the **basic space Ω**:
- Phenomenon is impossible is the set is empty. In the given conditions there is not state in which the phenomenon becomes true.
- Phenomenon is certain if the subset is equal to the basic space.
#### Intersection of Phenomenon
An intersection of phenomenon **A** and **B** is a phenomenon that will occur once both phenomenon **A** and **B** happen simultaneously. We can note it as **A ∩ B** and if **A ∩ B = ∅** then we say these phenomenon's are **disjunctive**.
#### Unification of Phenomenon
An unification of phenomenon **A** and **B** is a phenomenon that will occur once at least one phenomenon **A** and **B** happens. We can note it as **A ∪ B**.
#### Opposite Phenomenon
Is the complementary phenomenon to a phenomenon **A** and happens when phenomenon **A** does not happen. We note is as **A’** and it applies that **A’ = Ω \ A**.
### Full Phenomenon System
Phenomenon's **A1, B1, ...**  create a full phenomenon system if **A1 ∪ A2 ∪ ··· = Ω**. Additionally it applies that if **Ai ∩ Aj = ∅, ∀i != j** then we say it is a **full system of disjunctive phenomenon's**.
### Axiomatic Definition of Probability
If **(Ω, A)** is a phenomenon array and P is set function defined on **A** with properties:
- **P(Ω) = 1**
- **P(a) >= 0 ∀a ∈ A**
- If **Ak ∈ A, k = 1, 2, ...** are disjunctive phenomenons.
Then we can say that:
$$
P( unification \ of \ A) = \sum_{i=1}^{\infty} P(A_{i})
$$
Function P is the **probability function** and the triple **(Ω, A, P)** is the **probability space**.
### Classical Definition of Probability
Classical probability is defined as the **division** (ratio) of **amount of all favourable phenomenons** against **amount of all possible phenomenons**.
$$
P(A) = \frac{|A|}{|\omega|}
$$
Where:
- **|A|** is the number of elements of a set of favourable phenomenons.
- **|Ω|** is the number of elements of a set of all possible phenomenons, basic space.
### Probability Properties
If **(Ω, A, P)** is the **probability space** then for **P** the properties are:
- **P(∅) = 0**
- **a, b ∈ A, a ∩ b = ∅** ⇒ **P(a ∪ b) = P(a) + P(b)**
- **a, b ∈ A** ⇒ **P(a ∪ b) = P(a) + P(b) - P(a ∩ b)**
- **a, b ∈ A, a ⊂ b** ⇒ **P(b - a) = P(b) - P(a)**
- **a, b ∈ A, a ⊂ b** ⇒ **P(a) <= P(b)**
- **a ∈ A** ⇒ **0<= P(a) <= 1**
- **a ∈ A** ⇒ **P(a') = 1 - P(a)**
- **a1, a2, ... ∈ A** ⇒ **P(∪ ai) <= ∑ ai**
### Conditional Probability
A probability of some experiment is dependent on the another probability. If **(Ω, A, P)** is the **probability space** and **b ∈ A, P(b) > 0** then:
$$
P(a|b) = \frac{P(a \ ∩ \ b)}{P(b)}
$$
We can say that this is a **conditional probability** of phenomenon **a** under the condition that phenomenon **b** happened.
#### Bayes' Formula
If we have phenomenons **a** and **b** and **P(b) != 0** then it applies that:
$$
P(a|b) = \frac{P(b|a)P(a)}{P(b)}
$$
### Addition of Probability
If phenomenons are independent of each other their intersections are going to be **zero**.
$$
P(A ∪ B ∪ C) = P(A) + P(B) + P(C) - P(A∩B) - P(B∩C) - P(A∩C) + P- P(A∩B∩C)
$$
## Random Variable
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
## Random Vector
Commonly the outcome of an experiment is an **n-tuple** of real numbers or an [[Vector]]. In that case we can say that it is a **vector of multiple random variables**. If **X** and **Y** are random variables defined on the **same probability space (Ω, A, P)** we can say that **(X, Y)** is a random vector.
### Combined Distribution Function
It is the same principle as **Distribution Function but with multiple variables**. We notate it as **F(X, Y)**. The same rules as for distribution function apply.
### Marginal Distribution Function
It is a distribution function of **one random variables from a random vector**. When describing the vector this way we assume that all other variables in the vector are certain (100%). If then we have a distribution function **F(X, Y)** then its marginal distribution function of **X** and **Y** will be:
$$ F(x) = P(X\leq x) = \lim_{ y \to \infty } F(x, y); \ x ∈ R $$
$$ F(y) = P(Y\leq y) =\lim_{ x \to \infty } F(x,y); \ y ∈ R $$
### Combined Probability Density Function
Same as **Probability Density Function**.
### Marginal Probability Function
All random variable, with the exception of one, are certain (100%).
$$p_{x}(x) = P (X = x) = \sum_{y} p(x,y); \ x ∈ R $$
$$p_{y}(y) = P (Y = y) = \sum_{x} p(x,y); \ y ∈ R $$

| x/y | 0    | 1    | 2    |
| --- | ---- | ---- | ---- |
| 0   | 0.42 | 0.12 | 0.06 |
| 1   | 0.28 | 0.08 | 0.04 |
$$p(x) = \sum_{y} p(x,y)$$

| x      | 0   | 1   |
| ------ | --- | --- |
| p_x(x) | 0.6 | 0.4 |
$$p(x) = \sum_{y} p(x,y)$$

| y      | 0   | 1   | 2   |
| ------ | --- | --- | --- |
| p_y(y) | 0.6 | 0.3 | 0.1 |
### Conditioned Distribution
If we have a **random discrete vector (X, Y)** with a combined distribution function **p(x, y)**. Function is a conditioned distribution function if for **X** conditioned by **Y** variable that was evaluated as **y**:
$$p(x|y) = P(X = x|Y = y) = \frac{p(x, y)}{p_{y}(y)}; \ p_{y}(y) > 0$$
And in the same vain for **Y**:
$$p(y|x) = P(Y = y|X = x) = \frac{p(x, y)}{p_{x}(x)}; \ p_{x}(x) > 0$$
If the **random vector (X, Y)** is **continuous** with a **combined density probability function f(x, y)**:
$$f(x|y) = \frac{f(x, y)}{f_{y}(y)} \ f_{y}(y) > 0$$
And in the same vain for **Y**:
$$f(y|x) = \frac{f(x, y)}{f_{x}(x)} \ f_{x}(x) > 0$$
If the variables are **independent** on each other then we can just multiply output of their **marginal function outputs**.
### Properties
#### Independency
Values **independent** of each other if the value of one does not influence the value of the other. This can for example be done such that they are defined on different ranges from each other such as **x ∈ {1, 2}** and **y ∈ {3, 4, 5}**.
#### Mean Value (E(X, Y))
We can calculate the mean values just for one variable or a combination of them. For **discrete vectors**:
$$E(X) = \sum_{x} x \times p_{x}(x)$$
$$E(Y) = \sum_{y} y \times p_{y}(y)$$
$$E(XY) = \sum_{x} \sum_{y} xy \times p(x, y)$$
For **continuous vectors**:
$$E(X) = \int_{-\infty}^{\infty} x \times f_{x}(x) \, dx $$
$$E(Y) = \int_{-\infty}^{\infty} y \times f_{y}(y) \, dy $$
$$E(XY) = \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} xy \times f(x, y) \, dy \, dx $$
#### Dispersion (D(X, Y))
Calculated in the same vain as for a **random variable**:
$$D(X) = E(X^2) - [E(X)]^2$$

$$D(Y) = E(Y^2) - [E(Y)]^2$$
$$D(XY) = E(XY^2) - [E(XY)]^2$$
## Probability Distribution
### Even Distribution
$$f(x) = {\frac{1}{b-a} \ \ for \ x ∈ (a,b); \ \ 0 \ \ for \ x \ !∈ (a,b)} $$
$$F(x) = {0 \ \ for \ x ∈ \leq 0; \ \ \frac{x-a}{b-a} \ \ for \ x ∈ (a,b); \ \ 0 \ \ for \ x \ \geq b} $$
### Normal Distribution
It is described by a **central limit sentence (CLT/CLV)**, which states that **a sum or an arithmetic mean value** of a **great enough amount of random independent** and not too wild random values always resembles a **normal distribution** of the random value.
$$ f(x) = \frac{1}{σ \sqrt{ 2 \pi }} \times e^{- \frac{(x- \mu)^{2}}{2σ^2}}$$
$$F(x) = \int_{-\infty}^{\infty} \frac{1}{σ \sqrt{ 2 \pi }} \times e^{- \frac{(t- \mu)^{2}}{2σ^2}} \, dt $$
### Exponential Distribution
It describes the **time between two independent occurrences of a given random phenomenon**.
$$f(x) = {\alpha \times e^{-\alpha x} \ for \ x \ > 0; \ \ 0 \ for \ x \ \leq 0;}$$
$$F(x) = { 1 - \times e^{-\alpha x} \ for \ x \ > 0; \ \ 0 \ for \ x \ \leq 0;}$$
### Poisons Distribution
A **discrete distribution** that describes the **amount of occurrences** of a random value in a **one time interval**.
$$ P(X = x) = \frac{\alpha^x}{x!}e^(-\alpha)$$
$$F(x) = \sum_{x_{i}\leq x} \frac{\alpha^{x_{i}}}{x!}e^(-\alpha)$$
### Binomial Distribution
A **discrete distribution** used to figure out what is the probability of number of trials succeeding **x** for a **n** trials.
$$P[X = x] = \binom{n}{x} p^x(1-p)^{(n-x)}$$
## Generation of Pseudorandom Numbers
### Types
- **Physical Source of Randomness** uses a sensor device (temperature, acceleration, position, lava lamps, ...) the number is generated through truly random variable. The issues with this approach can be speed as the system can be restricted in the way it collect information.
- **Algorithm Generator** generate pseudorandom (deterministic) number. These do not have the issue of throughput, but suffer from determinism and loops.
### Congruency Generator
Uses constants **a**, **b** that must be chosen carefully otherwise it will lead to poor quality numbers. The final number is also cut into a shape using **mod m**, where **m** is the desired length.
$$x_{n+1} = (ax + b) mod \ m$$
They generate:
- **Even Distribution**
- **A finite amount of elements in order** - they have a period by which they cycle.
#### Requirements
- **Distribution Evenness**
- Statically **independency of the generated ordered set**
- The **longest period**
- Speed
### Mersenne Twister

### Xorshift
## Transformation into Different Distributions
Random and pseudo generators generate ideal numbers through **even distribution**, but during calculations we commonly need other distributions.
### Inverse Transform
Ideal method for generation of distribution is given analytically using the **inverse distribution function** of the **target distribution**. Commonly though the distribution function is unknown or cannot be **described by an inverse function of elementary functions**.
### Disjunctive Method
With a series of tests we look for a number that will satisfy the density function of the final distribution. The method is not suited for **infinite (not-constricted) distributions**, where a big part of the density is **concentrated in on a small interval**. For us to be able to implement this method for distribution generation, we must know the interval (both **x** and **y**). The method functions on the principle that we generate two pseudorandom numbers **x** and **y**, **x** get put into the **probability distribution function** and then we compare the outcome to **y**. If it is smaller then **x** is returned as a **value of the random value**, if not then we repeat the process. An issue might become the number of iteration for a incorrect distribution.
### Composition Method
A **complicated density function** (or even distribution) can be divided into several more simple intervals. For each interval can be used a different method for generating a distribution.
## Point and Interval Parameter Estimations
We have two sets:
- **Base Set** (population) that contains all defined units.
- **Selective Set** (selection of population) that contains some of the define units.
Through **properties** of the **selective set** we can **generalize the entire base**. This is for example used in **election polling** where we use **1000 asked voters** through which we can **estimate the distribution for all 8 milion voters**.
### Point Estimation
An **unknown parameter** (for example the mean value) of the **base set** can be estimated using a single value (point) of the **selective set**. A point estimation of a parameter of the base set are the **describing characteristics of the selective set**. 
An example could be:
	If the unknown parameter of the base set is the average voltage on 10 000 new batteries, then we can select 200 batteries (selective set), measure the selective set and get the mean value from it.
A point estimation will nearly never be the true (correct) value of the unknown parameter. A  better estimation is such that has a distribution is more concentrated on the unknown parameter, in other words has a **lower distribution**, or more specifically **lower standard deviation**.
#### Unbiased Estimation
An estimation is unbiased if it does not undervalue or overvalue the true value of the parameter. It cannot guarantee a good estimation, but it can eliminate **systematic errors**. The selective mean and dispersion are unbiased if only the dispersion is unbiased.
#### Consistent Estimation
It is a good estimation that is getting close to the true value of the parameter with the increasing amount of observations we make.
#### Mean Square (Quadratic) Error
It allows us to measure the transference of the point estimation and it combines the **dispersion** and **deviation**. 
$$MSE = \frac{1}{n} \sum _{i=1}^{n}(X_{i} - average(X))^2$$
#### Selective Average
$$average(X_{n}) = \frac{1}{n} \sum_{i=1}^{n} X_{i}$$
#### Selective Dispersion
$$s^2 = \frac{1}{n-1} \sum _{i=1}^{n}(X_{i} - average(X))^2$$
### Interval Estimation
Because **Point Estimation** is quite inaccurate in practice **Interval Estimation** is commonly used. With interval estimation we can say with some probability (usually high) that the value of an unknown parameter is in an interval.
The reliability of a given estimation is given (selected) by the probability of the interval of reliability. The higher the interval is, the more reliable the estimation is. The more the estimation is accurate (reliable) the wider the interval will be. The wider the interval is, the more the estimation is reliable, but then it is less accurate, which is impractical. Between accuracy and reliability is an uneven relation.
An interval estimation of a normal distribution can be calculated as:
$$ CI = average(x) \pm z \times \frac{σ(X)}{\sqrt{ n }}$$
Where:
- **average(x)** is the average of the selective set.
- **z** is the confidence level read from a table using the percentage of how sure we want to be.
- **σ(X)** is the standard deviation.
- **n** is the sample size.