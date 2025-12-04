---
tags:
  - IFJ
  - TIN
aliases: DSA
---
[[Stack Automata]] that can move from one **configuration** to another only through one rule. This means that for every rule its left side must be unique. This means that for each $q\in Q$ and $z\in \Gamma$ it applies that either:
- $\forall a\in \Sigma:|\sigma(q,a,z)|\leq 1 \wedge \sigma(q,\epsilon,z) = \emptyset$
- $\forall a\in \Sigma:\sigma(q,a,z) = \emptyset \wedge |\sigma(q,\epsilon,z)| \leq 1$
If $L = L(P)$, where $P$ is a deterministic stack automata, then the language $L$ is then called a deterministic context-free language. Deterministic stack automata are strictly less powerful then non-deterministic stack automata.
## Deterministic Context-Free Language Properties
Deterministic context-free languages are closed to operations:
- $\cap$ with [[Regular Language|regular languages]].
- Complement
Are not closed to operations:
- $\cap$
- $\cup$
- $.$
- $*$