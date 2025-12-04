---
tags:
  - MSP
aliases:
  - statistical inference
---
Statistical inference is an apparatus for answering questions for answering statistical questions (problems) based upon already existing collections of known results.
## Definitions
A statistical inference is a procedure that produces a probabilistic statement about some or all parts of a statistical model.
### Statistical Model
A statistical model consists of an identification of random variables, the identification of any parameters of those distributions that are assumed unknown and possibly hypothetically observable, and (if desired) a specification for a (joint) distribution for the unknown parameter(s). When we treat the unknown parameter(s) $\theta$ as random, the the joint distribution of the observable random variables indexed by $\theta$ is understood as the conditional distribution of the observable random variable given $\theta$.
### Parameter Space
In a problem of a statistical inference, a characteristic or combination of characteristics that determine the joint distribution for the random variables of interest is called a parameter of the distribution. The [[Set|set]] $\Theta$ of all possible values of a parameter $\theta$ or of a vector of parameters $(\theta_{1},\dots,\theta_{k})$ is called the parameter space.
### Statistic
Suppose that the observable independent identically distributed (IID) random variables of interest $X_{1},\dots,X_{n}$. Let $r$ be an arbitrary real-valued function of $n$ real variables. Then the random variable $T=r(X_{1},\dots, X_{n})$ is called a statistic.