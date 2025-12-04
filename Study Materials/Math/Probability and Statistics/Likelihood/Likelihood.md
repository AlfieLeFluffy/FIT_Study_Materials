---
tags:
  - MSP
aliases:
  - likelihood
  - likelihood estimators
---
## Definitions
### Likelihood Function
When the joint PDF or the joint PMF $f_{n}(x,\theta)$ of the observations in a random sample is regarded as a function of $\theta$ for given values of $x_{1},\dots,x_{n}$, it is called the likelihood function.
In notation we have the likelihood function described as $L(\theta)=f_{n}(x,\theta)$ and logarithmic likelihood function as $l(\theta)=\ln(L(\theta))$.
### Maximum Likelihood Estimation
For each possible observed vector $x$, let $\delta(x) \in \Theta$ denotes a value of the $\theta\in \Theta$ for which the likelihood function $L(\theta)$ is a maximum, and let the $\hat{\theta}=\delta(X)$ be the estimator of $\theta$ defined in this way. The estimator $\hat{\theta}$ is called the maximum likelihood estimator of $\theta$. After $X=x$ is observed the value $\delta(x)$ is called a maximum likelihood estimate of $\theta$.
To calculate the maximum likelihood estimator or estimation, the first derivation of $l(\theta)$, $l(\theta)'$ can be used such as $l(\theta)'=0$. If the first derivation is not parametrized by $x_{i}$ then there is no maximum likelihood estimation. 
### Bayesian Estimation
The main idea is to utilize Bayes' theorem to include some form of prior information about the parameters that is known into the estimation process.
$$\xi_{post}(\theta,x)= \frac{L(\theta)\xi_{pri}(\theta)}{g_{n(x)}}$$
To obtain an estimate from a $\xi_{post}$, different loss functions can be utilized.
### Regularity Condition
Let $\{ f(x,\theta), \theta\in \Theta \}$ be a system ([[Set|set]]) of PDFs (PMFs). This system is regular if the following conditions are met:
- Parametric space $\Theta$ is non-empty, open set.
- A [[Set|set]] $M=\{ x:f(x,\theta)>0 \}$ does not depend on the value of $\theta$.
- For each $x\in M$ a finite partial derivative $f'(x,\theta)=\frac{df(x,\theta)}{d\theta}$ exists.
- For all $\theta \in \Theta$ holds $\int_{M}f'(x,\theta)dx=0$.
- Integral $$J_{n}(\theta)=\int_{M}\left[ \frac{f'(x,\theta)}{f(x,\theta)} \right]^2f(x,\theta) dx$$ is finite and positive.
### Consistent Estimator
A sequence of estimators that converges in probability to the unknown value of the parameter being estimated, as $n\to \infty$, is called a consistent sequence of estimators. Maximum likelihood estimations satisfying regularity conditions form a consistent sequence of estimators.
### Unbiased Estimator
Let statistic $\delta(X)$ be an estimator of a function $g(\theta)$. We say that $\delta(X)$ is unbiased if $E_{\theta}[\delta(X)]=g(\theta)$ for all values of $\theta$.
An arithmetic mean $\overline{X}$ is an unbiased estimator for parameter $\mu$ in [[normal distribution]].
### Jensen's Inequality
Let $g$ be a strictly convex (concave) function and let $X$ be a random variable with finite mean, then $E[g(X)] > g[E(X)]$ ($E[g(X)] > g[E(X)]$).