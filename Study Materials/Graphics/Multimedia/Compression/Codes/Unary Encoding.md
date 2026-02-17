---
tags:
  - MUL
aliases:
  - UE
  - unary encoding
sources:
  - "[[MUL_02_Compression_Techniques.pdf]]"
---
A very simple entropic encoding.
## Characteristics
Basic UE characteristics are:
- Optimal for $p(n) = 2^{-n}$
- Maps non-negative whole numbers $N$ to bite codes.
- For example $N\to N*1,0$ such as: 
	- `0` -> `0` 
	- `1` -> `10`
	- `2` -> `110`
	- `3` -> `1110`
- 0 and 1 can be exchanged.