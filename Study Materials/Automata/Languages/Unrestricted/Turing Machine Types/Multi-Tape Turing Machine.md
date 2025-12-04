---
tags:
  - TIN
aliases:
  - multi-tape turing machine
  - MTM
---
A [[Turing Machine]] type that uses multiple tapes with tape [[Alphabet|alphabets]] $\Gamma_{1},\Gamma_{2},\Gamma_{3},\dots,\Gamma_{k}$, where $k$ is the amount of heads/tapes with the transitional function:
$$\sigma:(Q\setminus{q_{f}})\times \Gamma_{1}\times\Gamma_{2}\times\dots \times \Gamma_{k}\to Q\times\Gamma_{1}'\times\Gamma_{2}'\times\dots \times \Gamma_{k}'$$
Importantly if there exists a multi-tape Turing machine $M$ there also exists a signle-tape Turing machine $M'$, such that $L(M) = L(M')$. Other important characteristic is that expanding the memory options does not expand the Turing machine's capabilities of accepting languages.