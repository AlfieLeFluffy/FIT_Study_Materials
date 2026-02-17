---
tags:
  - MUL
aliases:
  - PE
  - predictive encoding
sources:
  - "[[MUL_02_Compression_Techniques.pdf]]"
---
An encoding type that uses prediction sequences.
## Characteristic
Basic characteristics of PE are:
- Encoded symbol is predicted from the previous symbol.
- It can also encode the prediction error.
- There are different degrees of predictors (1., 2., 3., ...).
- The are different domains (1D, 2D, [[Tree|trees]]).
### Predictor
The predictors can be:
- Linear ([[Diference Encoding]], Lossless, JPEG, PNG)
- Nonlinear (media, MED/LOCO-I, Paeth, GAP)