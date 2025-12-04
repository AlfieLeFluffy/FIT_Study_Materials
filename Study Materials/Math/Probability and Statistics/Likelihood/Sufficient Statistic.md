---
tags:
  - MSP
aliases:
  - sufficient statistics
  - sufficient statistic
---
## Definitions
Let $X$ be a random vector of independent identically distributed random variables, then $T$ is called a sufficient statistic for parameter $\theta$, if the conditional joint PDF (PMF) of $X$ given $T=t$ does not depend on $\theta$.
Let $T(X)$ be a sufficient statistic for the parameter $\theta$ and let $g(T(X))$ be a measurable one-to-one function, then $g(T(X))$ remains sufficient statistic for the parameter $\theta$.
### Factorization Criterion
Let $r_{1},\dots,r_{k}$ be functions of $n$ real variables. The statistic $T_{i}=r_{i}(X),i=1,\dots,k$ are jointly sufficient statistics for $\theta$ if and only if the joint PMF or the joint PDF $f_{n}(x,\theta)$ can be factored as the follows for all values of $x\in \mathbb{R}^n$ and all values of $\theta\in \Theta$: 
$$f_{n}(x,\theta)=u(x)v[r_{1}(x),\dots,r_{k}(x),\theta]$$
Here the functions $u$ and $v$ are non-negative, the function $u$ may depend on $x$ but does not depend on $\theta$, and the function $v$ will be dependent on $\theta$ but does not depend on $x$ only through the $k$ functions $r_{1}(x),\dots,r_{k}(x)$.
## Exponential Family
### General Definition
If the PDF or PMF can be expressed as follows, we say that the random variable belongs to the exponential family.
$$f(x,\theta)=h(x)\exp(\eta(\theta)\times T(x)-A(\theta))$$
Where:
- $h(x)$ is a function of the data $x$ that does not depend on the parameter $\theta$.
- $\eta(\theta)$ is the natural parameter.
- $T(x)$ is a function of $x$.
- $A(\theta)$ is the log-partition function, ensuring that the PDF (PMF) integrates (sums) to 1.
### Location/Scale Definition
If the PDF or PMF can be expressed as follows, we say that the random variable belongs to the exponential family.
$$f(x,\theta,\phi)=h(x)\exp\left\{ \frac{1}{\phi}[\eta(\theta)\times x-B(\eta(\theta))]+c(x,\phi) \right\}$$
Where:
- $h(x)$ is a function of the data $x$ that does not depend on the parameters $\theta$ and $\phi$.
- $\phi$ is a dispersion parameter.
- $\eta(\theta)$ is the natural parameter.
- $c(x,\phi)$ is a function of $x$ and a dispersion parameter $\phi$.
- $B(\eta(\theta))$ is strictly convex twice differentiable function.
### Estimation
If a probability distribution belongs to the exponential family, the minimal sufficient statistics exists and can be found using the factorization criterion.
Moments of the distribution of the exponential family can be derived as:
- $E[X]=\frac{d}{d \eta(\theta)}B(\eta(\theta))$
- $Var[X]=\phi \frac{d^2}{d[\eta(\theta)]^2}B(\eta(\theta))$