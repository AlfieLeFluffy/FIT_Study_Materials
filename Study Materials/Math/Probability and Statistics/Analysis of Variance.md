---
tags:
  - MSP
aliases:
  - analysis of variance
  - ANOVA
---
## Definition
Since a model $U_{n\times_{1}}=1_{n\times_{1}}$ is a [[Linear Model#Sub-Model|sub-model]] of any parametrization of a model with more different means, using the [[F-Distribution]] statistic to test submodel $1_{n\times_{1}}$ against the full model with design matrix $X$ is testing $H_{0}:\mu_{1}=\mu_{2}=\dots=\mu_{k}$ against $H_{1}: \exists i,j:\mu_{i}\not=\mu_{j}$. 
### Table

| Source of Variation | Degrees of Freedom (df) | Sum of Squares (S) | Mean Square (MS)            | F-value             |
| ------------------- | ----------------------- | ------------------ | --------------------------- | ------------------- |
| Factor A            | $df_{A}$                | $S_{A}$            | $MS_{A}={S_{A}} / {df_{A}}$ | $F=MS_{A} / MS_{e}$ |
| Error               | $df_{e}$                | $S_{e}$            | $MS_{e}={S_{e}} / {df_{e}}$ |                     |
| Total               | $df_{T}$                | $S_{T}$            |                             |                     |
For sums of squares in One-way ANOVA the following equality hold $S_{T}=S_{A}+S_{e}$.
### Formulas
Let $n$ be a total number of observations and $n_{j}$ be a number of observations belonging to $j^{th}$ group, then:
$$S_{T}=\sum^n_{i=1}(y_{i}-\overline{y}^2)=\sum^n_{i=1}(y_{i}^2)-n\overline{y}^2$$
$$S_{A}=\sum^k_{j=1}n_{j}(\overline{y}_{j}-\overline{y})^2$$
$$S_{e}=S_{T}-S_{A}$$
## Multiple Comparison Error Handling
Assume all assumptions for a One-way ANOVA are met and a [[Linear Model#Sub-Model|Sub-Model]] test rejected the null hypothesis that all (subgroup means) are equal. There are several (viable) approaches to test the pairwise differences:
- **Fisher's**: Since you rejected the submodel for ANOVA, you should check for all significant differences at the original $\alpha$ level (Least Significant Difference - LSD)
- **Tukey's**: The initial test does not convey enough evidence so join probability of type I. error should be original $\alpha$ (Honest Significant Difference - HSD).
- **Special**: Use apriori known information to reduce the necessary amount of comparisons. Dunnet's (one of the groups in control group - reference for all), Hsu's (it is clear that higher/lower values are better).
### Least Significant Difference
If you want to use Fisher's LSD, you just need to repeatedly compute "modified [[T-Test]]" for 2 independent samples at a given significance level $\alpha$. So to compare groups $j$, $i$ test $H_{0}:\mu_{j}=\mu_{I}$ and if $H_{0}$ holds: $$T= \frac{\overline{Y_{j}}-\overline{Y_{i}}}{S_{res}\sqrt{ \left( \frac{1}{n_{j}} + \frac{1}{n_{i}} \right) }}$$
Difference to ordinary [[T-Test|t-test]] for 2 independent samples (with the same variance) is in using pooled estimate for $\sigma$ for all groups.
### Honest Significant Difference
To use Tukey's method, it is necessary to define "Studentized range" and its probability distribution.
Studentized range (Tukey's HSD) can be defined as: let $X_{1},\dots,X_{k}$ be independent normally distributed variables $X_{i}\approx N(\mu,\sigma^2)$, let $s^2$ be an independent estimator for $\sigma^2$ with $v$ degrees of freedom, then:
- $Q= \frac{max(X_{i})-min(X_{i})}{s}$ is a Studentized range with parameters $k,v$ and distribution ($q_{k,v}$).
- Now assume that you can get $n_{i}$ observations for each $X_{i}$. Under $H_{0}:\mu_{1}=\dots=\mu_{k}$ it holds for all $j,i$:$$P\left( |\overline{X_{j}} - \overline{X_{j}}|<S_{res}q_{k,n-k}\left( \alpha \sqrt{ \frac{1}{2}\left( \frac{1}{n_{j}}+\frac{1}{n_{i}} \right) } \right) \right)<1-\alpha$$
### Scheffé's Comparisons
![[Scheffé's Comparisons]]
### Bartlett's Test
![[Bartlett's Test]]
### Testing for Normality of Resiguals
- Comparing skewness and (excess) kurtosis to normal distribution (Jarque-Berra, Omnibus)
- Utilizing empirical distribution function (Cremér-von Mises test "family" e.g. Kolmogorov-Smirnov, Liliefors, Anderson-Darling)
- Utilizing order statistics (Shapiro-Wilk)
- Discretizing and reformulating the problem as multinomial distribution (Pearson's goodness of fit test)
### Skewness and Excess Kurtosis
![[Skewness and Excess Kurtosis]]
### Jarque-Berra Test
![[Jarque-Berra Test]]
## Interaction
Interaction is a simultaneous effect of two or more factors, that can not be explained using any of the factors by themselves.
