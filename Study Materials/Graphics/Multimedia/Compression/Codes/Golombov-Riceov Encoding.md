---
tags:
  - MUL
aliases:
  - GRE
  - Golombov-Riceov encoding
sources:
  - "[[MUL_02_Compression_Techniques.pdf]]"
---
It is a special quick implementation of Golombov encoding.
## Characteristics
Basic characteristics of GRE are:
- Used in formats such as JPEG-LS, FLAC, MPEG-4 ALS.
- Maps non-negative whole numbers $\mathbb{N}$ to bite codes.
- The code is parametrized by parameter $M=2^C$ and for $M=1$ it become [[Unary Encoding]].
- To obtain the code of number $N$ it is first evaluated:
$$Q= \lfloor N/M\rfloor$$
$$R= N-Q\times M$$
$$Q= \lceil \log_{2}(M) \rceil $$
- Q is encoded through [[Unary Encoding]], R through binary and C as bitech.