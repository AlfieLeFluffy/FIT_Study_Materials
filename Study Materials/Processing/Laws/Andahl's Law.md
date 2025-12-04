---
tags:
  - AVS
  - to_be_finished
aliases:
  - Andahl's law
---
Computing/processing law that dictates efficiency with parallelization of work on [[Microprocessor]]s. It separates work into two sections:
- **Sequential part** that uses 1 [[Microprocessor|CPU]], cannot be paralyzed and the amount is usually signified by **αW**, where α is the ration of work that is sequential (0.1, 0.5, 0.25) and W is the full amount of work.
- **Parallelizable part** that can use P CPUs and is signified by **(1-α)W**, inverse of the previous amount.
The equation for the speed-up coefficient is:
$$S(P) = \frac{T_{s}}{T(P)} = \frac{W / R}{W\left( \frac{\alpha}{R}+\frac{1-\alpha}{P\times R} \right)} = \frac{P}{1+\alpha(P-1)}$$
The speed-up coefficient is limited as such:
$$\lim_{ P \to \infty } S(P) = \frac{1}{\alpha} $$
and effectivity as such:
$$\lim_{ P \to \infty } E = 0$$
---
## Source
- [[AVS_01_Scalar_Processors.pdf#page=10]]