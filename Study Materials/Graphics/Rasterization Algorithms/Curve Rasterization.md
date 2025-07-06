Curves are represented by a set of points and can be divided into two types:
- **Interpolation** - the curve has to go through the control points.
- **Approximation** - the curve does not have to go through the control points, which we also call **Bezier curves**
## Bezier (Beziérovy) Curves
Approximation curves that used in 2D graphics and more specifically in fonts.
### Properties
- Polynormal curve that uses Bernstein polynomial.
- Curve of **N** level is described by **N+1** points.
- The curve goes through the end points.
### Recurrent Definition
We can recurrently define the curve with **Bernstein polynomial**, which is used for fonts.
- Q(t) = ∑<sup>n</sup><sub>i=0</sub> P<sub>i</sub> * B<sup>n</sup><sub>i</sub>(t); i = 0, 1, ..., n
- B(t) = ( <sup>n</sup> <sub>i</sub> ) t<sup>i</sup> (1 - t)<sup>n-i</sup>; t ∈ <0, 1>
Where:
- B<sub>0</sub> (t)= (1 - t)<sup>3</sup> 
- B<sub>1</sub> (t)= 3t(1 - t)<sup>2</sup> 
- B<sub>2</sub> (t)= 2t<sup>2</sup>(1 - t)
- B<sub>3</sub> (t)= t<sup>3</sup> 
So if put together:
- P(t) = P<sub>0</sub>B<sub>0</sub> (t) + P<sub>1</sub>B<sub>1</sub> (t) + P<sub>2</sub>B<sub>2</sub> (t) + P<sub>3</sub>B<sub>3</sub> (t)
- P(t) = ∑<sup>3</sup><sub>i=0</sub> P<sub>i</sub> * B<sub>i</sub>(t)
## De Casteljau Algorithm
A **recursive** algorithm that is used to rasterize **Bezier curves**.
### Princip
- A small enough step **t** is chosen. The range that t will travel is <0,1>.
- Each segment of the polynom is divided by ration of **t** and **t-1** and in the place of the division a new point is created used for next division. With each step the polynom's level decreases until only one point remains.
- The resulting points are connected together through [[Line Rasterization]].
## Bezier's Cubics
Bezier curve of 3. stage is described by a Bernstein's polynom of 3. stage. A segment is thus described through 4 control points.
### Princip
- **Divide and Conquer** - Uses the De Casteljau in combination with Bezier Cubics. Recursively divides the problem into two sub-curves. A straight enough curve is not divided anymore and instead is rasterized.
### Connecting Segments of Bezier Cubics
To connect segments made through the cubics they require the same end point and the same tangent vectors. The end point is the middle of the line before the near to last point of the first curve and the second point of the second curve.