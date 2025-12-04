---
tags:
  - IPT
  - MSP
aliases:
  - random vector
---
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
#### Sum Rule
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
#### Product Rule
$$p(x,y) = p(x|y)p(y) = p(y|x)p(x)$$
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
