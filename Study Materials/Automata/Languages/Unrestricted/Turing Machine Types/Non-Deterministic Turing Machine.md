---
tags:
  - TIN
aliases:
  - non-deterministic turing machine
  - NTM
---
A non-deterministic [[Turing Machine]] type that is similar in most aspect to the normal one, with the exception of the transitional functions that is:
$$\sigma: (Q\setminus \{ q_{f} \})\times \Gamma\to 2^{Q\times(\Gamma \cup \{ L,R \})}$$
A [[Formal Language|language]] $L(M)$ is accepted by the non-deterministic Turing machine if for a simulation of all strings $w \in \Sigma^*$ can stop by transitioning into the final state $q_{f}$.
Importantly, for any non-deterministic Turing machine $M$ there exist a deterministic Turing machine $M'$, such that $L(M) = L(M')$. Other important characteristic is that expanding the memory options does not expand the Turing machine's capabilities of accepting languages.