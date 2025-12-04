---
tags:
  - IPT
aliases:
  - distribution transformation
  - transformation of distributions
---
## Transformation into Different Distributions
Random and pseudo generators generate ideal numbers through **[[even distribution]]**, but during calculations we commonly need other distributions.
### Inverse Transform
Ideal method for generation of distribution is given analytically using the **inverse distribution function** of the **target distribution**. Commonly though the distribution function is unknown or cannot be **described by an inverse function of elementary functions**.
### Disjunctive Method
With a series of tests we look for a number that will satisfy the density function of the final distribution. The method is not suited for **infinite (not-constricted) distributions**, where a big part of the density is **concentrated in on a small interval**. For us to be able to implement this method for distribution generation, we must know the interval (both **x** and **y**). The method functions on the principle that we generate two pseudorandom numbers **x** and **y**, **x** get put into the **probability distribution function** and then we compare the outcome to **y**. If it is smaller then **x** is returned as a **value of the random value**, if not then we repeat the process. An issue might become the number of iteration for a incorrect distribution.
### Composition Method
A **complicated density function** (or [[even distribution]]) can be divided into several more simple intervals. For each interval can be used a different method for generating a distribution.