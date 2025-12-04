---
tags:
  - AVS
  - to_be_finished
aliases:
  - Gustafson's law
---
With a growing size of the work **W** it relatively often means **α** shrinks and we get a better speed-up coefficient. For a constant **time T<sub>P</sub>**, of  which **αGT<sub>P</sub>** is sequential work on 1 [[Microprocessor|CPU]] and **(1-α<sub>G</sub>)T<sub>P</sub>** is paralysed work on **P** CPUs, the speed-up and efficiency coefficients are:
$$S = \frac{T_{S}}{T_{P}} = \frac{\alpha_{G}T_{P}+P(1-\alpha_{G})T_{P}}{T_{P}} = P - \alpha_{G} (P-1)$$
$$E = 1 - \alpha_{G} + \frac{\alpha_{G}}{P}$$
The efficiency is limited as:
$$\lim_{ P \to \infty } E = 1 - \alpha_{G} $$
---
## Source
- [[AVS_01_Scalar_Processors.pdf#page=11]]