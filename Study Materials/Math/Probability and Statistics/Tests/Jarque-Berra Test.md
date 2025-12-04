---
tags:
  - MSP
aliases:
  - Jarque-Berra test
  - Jarque-Berra
---
## Definition
Assume that $X_{1},\dots,X_{n}$ are independent normally distributed [[Random Variable|random variables]]. Then $$JB=\frac{n}{\sigma}\left( Skew^2+\frac{1}{4}Kurt^2 \right)$$ asymptotically follows [[Chi Distribution|chi distribution]] with 2 degrees of freedom.
This time recommended $n$ for the asymptotic distribution to hold is $n>2000$. For lower $n$ it is recommended to use Omnibus test. Jarque-Berra test increases type I error over specified $\alpha$ for "small" sample sizes.