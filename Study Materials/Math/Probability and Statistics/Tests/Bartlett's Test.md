---
tags:
  - MSP
aliases:
  - Bartlett's
  - Bartlett's test
---
## Definition
Assume that all groups from One-way [[Analysis of Variance|ANOVA]] follows a normal distribution with the same variance $\sigma^2$. Let for each category $j\in \{ 1,2,\dots,k \}$ be $s_{j}^2=\frac{1}{n_{j}-1}\left( \sum_{i=1}^{n_{j}}Y_{i}^2 - n_{j}\overline{Y}^2_{j} \right)$ and let's define $C=1+\frac{1}{3(k-1)}\left( \left( \sum_{j=1}^k \frac{1}{n_{j}-1} \right) - \frac{1}{n-k} \right)$, then (if all $n_{j}>6$) $$B=\frac{1}{C}\left[ (n-k) \ln(S^2_{res})-\sum_{j=1}^k(n_{j}-1)\ln(s_{j}^2)\right]$$ follows approximately [[Chi Distribution|chi distribution]] with $k-1$ degrees of freedom.