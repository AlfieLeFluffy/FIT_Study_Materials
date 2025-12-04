---
tags:
  - MSP
aliases:
  - Scheffé's
  - Scheffé's comparisons
---
## Definition
Assume that all [[Analysis of Variance|ANOVA]] assumptions hold, then if $H_{0}:\mu_{j}=\mu_{i}$ holds, the following fraction follows Fisher-Snedecor distribution.
$$\frac{\frac{(\overline(Y_{j})-\overline(Y_{i})^2)}{k-1}}{S_{res}^2\left( \frac{1}{n_{j}} +\frac{1}{n_{i}}\right)}$$
Sheffé's comparisons are generally weaker than Tukey's, but handle joint $\alpha$ the same way (Family Wise Error Rate is $\leq \alpha$).