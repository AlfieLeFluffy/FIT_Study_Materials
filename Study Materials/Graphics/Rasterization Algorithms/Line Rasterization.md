---
tags:
  - IZG
  - PGR
aliases:
  - line rasterization
---
Rasterization of lines is done through algorithms that can usually only draw a line in the 1. kvadrant and only if the line has a lower angle then 45 degrees (the X coordinate grows quicker then Y). For every other direction the line is still in that direction but when writing down pixels the coordinates get flipped around.
## DDA (Digital Differential Analyzer)
Uses floating point arithmetic.
### Princip
- Generates a line from point $P_{1}$ to $P_{2}$.
- In the $X$ axis the algorithm increments with $dx = 1$.
- In the $Y$ axis the algorithm increments with size of the directive equation meaning $dy = k = (y_{2} - y_{1})/(x_{2} - x_{1})$.
- The coordinate for $Y$ is rounded to the closest whole number (usually $int(y + 0.5)$)
## DDA With Fixed Point Arithmetic
Eliminates the need for floating point arithmetic by doing a bit shift (`y1 << FRAC_BITS`) for both the $Y$ axis value and the size of the directive equation and then does an inverse bit shift (`y1 >> FRAC_BITS`)once writing pixels. Otherwise the algorithm function exactly like DDA. 
## Midpoint (Brenham) Algorithm
Uses whole number arithmetic, which is easier for [[Hardware]] implementation, which is why is the most common algorithm today. 
### Princip
- Generates a line from point $P_{1}$ to $P_{2}$.
- In the $X$ axis the algorithm increments with $dx = 1$.
- In the $Y$ axis the algorithm increments based on the sign of a predicate: $P_{i} = 2\Delta xE_{i} + 2\Delta y - \Delta x$. If the value is greater or equal to $0$ then we increment $x$ and $y$ (and do $P_{i+1} = P_{i} + 2\Delta y - 2\Delta x$) otherwise we only increment $x$ (and do $P_{i+1} = P_{i} + 2\Delta y$).