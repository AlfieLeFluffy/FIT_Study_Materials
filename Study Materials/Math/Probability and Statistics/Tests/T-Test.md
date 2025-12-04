---
tags:
  - IPT
  - MSP
aliases:
  - t-test
  - T-test
---
## Definition
Let $X_{1},\dots,X_{n}$ be independent identically normally distributed [[Random Variable|random variables]] and it is required to [[Hypothesis Testing|test]] a hypothesis $H_{0}:\mu=\mu_{0}$ against $H_{1}:\mu\not=\mu_{0}$. Then if $H_{0}$ is true, the following test statistic follows $t(n-1)$ [[Student's T-Distribution|t-distribution]].
$$\frac{{\overline{X}-\mu_{0}}}{\sqrt{ S^2(X) }}\sqrt{ n }$$
To construct a rejection region it is necessary to get quantiles of [[Student's T-Distribution|t-distribution]]. $W_{\alpha}=(-\infty;-t_{1-\alpha/2})\cup(t_{1-\alpha/2};\infty)$. Alternatively you can use a set complement to rejection region $\overline{W}=(-t_{1-\alpha/2};t_{1-\alpha/2})$.
### One-Sided Alternatives
It can be useful to construct the alternative hypothesis in a way that it detects only that $\mu>\mu_{0}$ or $\mu<\mu_{0}$. For the t-test, this can be handled just by adjusting the rejection region.
For $H_{0}:\mu=\mu_{0}$ with $H_{1}:\mu>\mu_{0}$ the rejection region will be $W_{\alpha}=(t_{1-\alpha};\infty)$.
For $H_{0}:\mu=\mu_{0}$ with $H_{1}:\mu<\mu_{0}$ the rejection region will be $W_{\alpha}=(-\infty,-t_{1-\alpha})$.