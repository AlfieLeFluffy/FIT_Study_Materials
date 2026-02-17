---
tags:
  - IZG
  - PGR
aliases:
  - curve rasterization
---
Curves are represented by a set of points and can be divided into two types:
- **Interpolation** - the curve has to go through the control points.
- **Approximation** - the curve does not have to go through the control points, which we also call *Bezier curves*
## Bezier Curves
Approximation curves that used in 2D graphics and more specifically in fonts.
### Properties
- Polynormal curve that uses Bernstein polynomial.
- Curve of $N$ level is described by $N+1$ points.
- The curve goes through the end points.
### Recurrent Definition
We can recurrently define the curve with **Bernstein polynomial**, which is used for fonts.
- $Q(t) = ∑^{n}_{n=0} P_{i} * B^{n}_{i}(t)$ where $i = \{0, 1, ..., n\}$
- $B(t) = ( P^{n}_{i} ) t^{i} (1 - t)^{n-i}$ where $t \in <0, 1>$
Where:
- $B_{0} (t)= (1 - t)^{3}$ 
- $B_{1} (t)= 3t(1 - t)^{2}$
- $B_{2} (t)= 2t^{2}(1 - t)$
- $B_{3} (t)= t^{3}$ 
So if put together:
- $P(t) = P_{0}B_{0} (t) + P_{1}B_{1} (t) + P_{2}B_{2} (t) + P_{3}B_{3} (t)$
- $P(t) = \sum^{3}_{i=0} P_{i} * B_{i}(t)$
## De Casteljau Algorithm
A **recursive** algorithm that is used to rasterize **Bezier curves**.
### Princip
- A small enough step $t$ is chosen. The range that t will travel is $<0,1>$.
- Each segment of the polynom is divided by ration of $t$ and $t-1$ and in the place of the division a new point is created used for next division. With each step the polynom's level decreases until only one point remains.
- The resulting points are connected together through [[Line Rasterization]].
## Bezier's Cubics
Bezier curve of 3. stage is described by a Bernstein's polynom of 3. stage. A segment is thus described through 4 control points.
### Princip
- **Divide and Conquer** - Uses the De Casteljau in combination with Bezier Cubics. Recursively divides the problem into two sub-curves. A straight enough curve is not divided anymore and instead is rasterized.
### Connecting Segments of Bezier Cubics
To connect segments made through the cubics they require the same end point and the same tangent vectors. The end point is the middle of the line before the near to last point of the first curve and the second point of the second curve.