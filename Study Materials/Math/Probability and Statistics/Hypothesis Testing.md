---
tags:
  - IPT
  - MSP
aliases:
  - hypothesis testing
---
Hypothesis testing is a process used to make decisions about some statements regarding statistical model. This can for example be:
- Is the true value of a parameter $\theta$ of assumed probability distribution some known value $\theta_{0}$?
- Do observations follow assumed probability distributions?
- Are the values of a parameter $\theta$ of assumed probability distribution the same for two disjoint groups in data?
Generally speaking you want to decide if some statement regarding properties of a statistical model (that are not directly observable) is likely to be true.
## Definitions
### Simple Null Hypothesis
A simple null hypothesis can be defined as if the hypothesis can be reduced to just a single value ($H_{0}: \theta=\theta_{0}$), then we call the hypothesis simple.
### Compounded Hypothesis
If a hypothesis is not simple then it is compounded.
### Hypothesis Testing
Let $X_{1},\dots,X_{n}$ be observed values for a distribution that depends on parameter $\theta$, let $T=r(X_{1},\dots X_{n})$ be a statistic and let W be a subset of a real line. Suppose that the test procedure is in the form: "reject $H_{0}$ if $T\in R$". Then we call $T$ test statistic (testing criterium) and $W$ the rejection region (critical set) of the test.
### P-Value
P-value is a probability of observing observed data, if the $H_{0}$ is true (and all assumptions of used statistical model hold). If the rejection region can be expressed from $T\geq c$ as an interval $<c;\infty)$, then the p-value is just a quantile function of the observed value of test statistic. 
## Process
The process of hypothesis testing works as:
1. Identify all necessary components  of a statistical model.
2. Decide on a sampling plan and significance level $\alpha$.
3. "Translate" the problem into the null and alternative hypothesis.
4. Observe the data.
5. Use the data to compute a test statistic or p-value (use the probability distribution for the statistic, conditioned on $H_{0}$ being true).
6. Considering resulting value, decide on rejecting or not rejecting $H_{0}$.
## Errors
There are two types of errors in hypothesis testing:
- **Type I** error happens if you reject null hypothesis that is true.
- **Type II** error happens if you do not reject a null hypothesis that is not true.
## Tests
![[T-Test]]