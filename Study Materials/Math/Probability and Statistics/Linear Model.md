---
tags:
  - MSP
aliases:
  - linear model
---
## Definition
Let $Y=(Y_{1},\dots,Y_{n})^T$ be a [[Random Vector|random vector]] (column), $X_{n\times k}$ given [[Matrix|matrix]] of constants (design matrix) and $\beta=(\beta_{1},\dots,\beta_{k})^T$ [[Vector|vector]] of parameters. $Y$ is governed by a linear model if:
- $E[Y]=Y\beta$
- $Var(Y)=V$ exists and is independent on $\beta$
It will be assumed further that $n>k$ for simplicity.
We call $b$ a linear estimator for a [[Vector|vector]] $\beta$ if a [[Matrix|matrix]] $U_{k\times n}$ exists in a way that $b=UY$.
### Gauss-Markov Theorem
Let the rank of a [[Matrix|matrix]] $X$ be $k$ and $V$ regular matrix, then efficient linear estimator $b$ for $\beta$ is: $$b=(X^TV^{-1}X)^{-1}X^TV^{-1}Y$$
with a veriance-covariance matrix:$$Var(b)=(X^TV^{-1}X)^{-1}$$
### Sub-Model
Let $M$ be a linear model under which $Y\approx N(X\alpha,\sigma^2I)$ and $M_{1}$ linear model under which $Y\approx N(U\beta,\sigma^2I)$. Let $X$ be of a type $n\times k$, $U$ of type $n\times k_{1}$, let rank $r(X)>r(U)$ and each column of $U$ can be expressed as a linear combination of columns in $X$. Then we call $M_{1}$ a submodel of $M$.
Let $a$, $b$ be estimates of $\alpha$, $\beta$ respectively and assume that $M_{1}$ is a correct model. Let $S_{e}=(Y-Xa)^T(Y-Xa)$ and let $S_{A}=(Xa-Ub)^T(Xa-Ub)$, then $$F=\frac{S_{A}/(r(X)-r(U))}{S_{e}/(n-r(X))}\approx F_{dist}((r(U)-r(X)),(n-r(X)))$$
## Known Linear Models
Let $c=(c_{1},\dots,c_{k})^T$ be a non-zero vector, then $E[c^Tb]=c^T\beta$ and $\hat{\theta}=c^Tb$ is an estimator for $\theta=c^T\beta$ with variance $Var(\hat{\theta})=c^T(X^TV^{-1}X)^{-1}c$.
We call a vector $e=(Y-Xb)$ residual vector and $S_{e}=e^Te$ a residual sum of squares.
$S^2_{res}=\frac{S_{e}}{n-k}$ is an unbiased estimator of $\sigma^2$.
Let $c=(c_{1},\dots,c_{k})^T$ be a non-zero vector and $Y_{n\times 1}\approx N(X\beta;\sigma^2I)$ then $$T=\frac{c^Tb-c^T\beta}{\sqrt{ s_{res}^2c^T(X^TX)^{-1}c }}\approx t(n-k)$$