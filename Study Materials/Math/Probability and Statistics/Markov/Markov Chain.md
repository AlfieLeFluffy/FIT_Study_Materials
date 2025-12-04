---
tags:
  - MSP
aliases:
  - markov chain
---
[[Random Variable]] that **evolves over time**. 
## Characteristics
Important characteristics of such variables are:
- **Finite** vs Countably Infinite vs Uncountably Infinite
- **Fully Observable** vs Parametric vs Partially Observable
- **Labelled Transition System**
## Probabilistic Models

|                 | fully probabilistic                        | non-deterministic                                            |
| --------------- | ------------------------------------------ | ------------------------------------------------------------ |
| discrete time   | [[Discrete-Time Markov Chains]](**DTMCs**) | [[Markov Decision Processes]] (**MDPs**)                     |
| continuous time | continous-time Markov chains (**CTMCs**)   | probabilistic timed automata (**PTAs**), **CTMDPs**/**IMCs** |
## System Input Modeling 
There are three main ways to model system input:
- **Deterministic** system
- **Transition** (Non-deterministic branching) system
- **Markov** (Probabilistic branching) chain
![[System_Input_Example.excalidraw.svg]]

---
### Sources
- [[MSP_01_Introduction_and_Makrov_chain.pdf]]
