---
tags:
  - IPT
  - MSP
aliases:
  - confidence interval
  - CL
---
## Definition
Let $X_{1},\dots,X_{n}$ be independent identically distributed variables, that depend on a parameter $\theta$ and $g(\theta)$ be a real valued parametric function. Let $A\leq B$ be two statistics that have a property $P(A\leq g(\theta)\leq B)\geq(1-\alpha)$. Then the random interval $(A,B)$ is called $(1-\alpha)$ confidence interval for $g(\theta)$.
### Example
Confidence interval of parameters of a [[normal distribution]] can be expressed as:
$$\delta^2\in\left( \frac{\sum_{i=1}^n(X_{i}-\hat{X}^2)}{\chi_{1-\alpha/2}^2};\frac{\sum_{i=1}^n(X_{i}-\hat{X}^2)}{\chi_{\alpha/2}^2} \right)$$
$$\mu\in\left( \hat{X}-\frac{S(X)}{\sqrt{ n }}t_{1-\alpha/2}; \hat{X}-\frac{S(X)}{\sqrt{ n }}t_{\alpha/2} \right)$$
where $S(X)=\sqrt{ \frac{1}{n-1} \sum_{i=1}^n (X_{i}-\hat{X})^2}$, $t_{1-\alpha/2}$ is $1-\alpha/2$ quantile of [[Student's T-Distribution|t-distribution]] with $n-1$ degrees of freedom and $\chi_{1-\alpha/2}^2,\chi_{\alpha/2}^2$ are corresponding quantiles of [[Chi Distribution|chi distribution]] with $n-1$ degrees of freedom.