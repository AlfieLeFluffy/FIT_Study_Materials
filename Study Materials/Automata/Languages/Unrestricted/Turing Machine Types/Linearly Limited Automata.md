---
tags:
  - TIN
aliases:
  - linearly limited automata
  - LLA
---
Linearly limited automata is a special kind of [[Turing Machine|Turing machine]] that will never leave the part of a tape onto which the input is written.
## Definition
Formally, a linearly limited automata is defined as a [[Non-Deterministic Turing Machine|non-deterministic Turing machine]], that has a specially symbol included in its tape [[Alphabet|alphabet]] $\Gamma$, that uniquely defines the right most edge (end) of the tape. This symbol cannot be overwritten and cannot be moved to the right if it is under the tape head.
A linearly limited automata can cycle.
### Determinism
A deterministic LLA can be naturally defined as a deterministic [[Turing Machine|Turing machine]] that never leaves the part of the tape with the written input, but it is unknown if it is or isn't weaker or stronger then normal LLA.
## Accepted Languages
Linearly limited automata can accept [[Context-Sensitive Language]].