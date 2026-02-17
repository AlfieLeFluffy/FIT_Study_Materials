---
tags:
  - TIN
aliases:
  - reduction
sources:
  - "[[TIN_09_Decidability.pdf]]"
---
Given $A$ and $B$ are [[Formal Language|languages]], $A \subseteq \Sigma^*, B \subseteq \Psi^*$. Reduction of language $A$ onto language $B$ is a total recursively enumerable funkce $\sigma: \Sigma^* \to \Psi^*$, such that $\forall w\in \Sigma^*|w\in A \Leftrightarrow \sigma(w) \in B$. If a reduction of language $A$ onto $B$ exists, then we say that $A$ is reducible onto $B$, which we signify as $A \leq B$. Given $A \leq B$, then:
- If $A$ is not recursively enumerable, then $B$ is also not recursively enumerable.
- If $A$ is not recursive, then $B$ is also not recursive.
- If $B$ is recursively enumerable, then $A$ is also recursively enumerable.
- If $B$ is recursive, then $A$ is also recursive.