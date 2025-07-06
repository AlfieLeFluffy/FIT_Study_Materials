We can define a circle by its center point and radius: **(x - s<sub>1</sub>)<sup>2</sup> + (y - s<sub>2</sub>)<sup>2</sup> = r<sup>2</sup>**
Calculations are done only for 1/8 of the circle with the rest being mirrored around to complete the full circle. All of the algorithms are derived for circles that have their center point at \[0,0\], so they have to shifted after generation.
## Point Generation
It is the easier for understanding and for generation, but it is quite intensive on the [[Hardware (HW)]]. It uses floating point arithmetic and generates the 1. kvadrant for an angle greater then 45 degrees, with the rest being symmetrically flipped around. The generation follows the direction of the clock, so in essence it generates from 12:00 to 1:30 and then fabricates the rest.
### Princip
1. The algorithm goes from the point **\[0,R\]** until **x = y**.
2. In the X axis the algorithm increments by **dx = 1**.
3. In the Y axis the algorithm calculates the y value as **y = √(R<sup>2</sup> - x<sup>2</sup>)**.
4. The y coordinate gets rounded to the closest whole number (usually done as **int(y + 0.5)**)
## Generation as a n-gon (polygon)
This algorithm uses [[Line Rasterization#DDA (Digital Differential Analyzer)|DDA]] to draw the circle as a polygon made out of many small lines. To to this the algorithm cuts the rasterized area into sections depending on **N** value and then draws lines between where these sections should meet to form a circle. This algorithm works in the opposite direction from Point Generation, essentially going from 3:00 to 12:00 and draws the full 1. kvadrant with the rest symmetrically mirrored.
## Midpoint Generation
Essentially the same algorithm as [[Line Rasterization#Midpoint (Brenham) Algorithm|Midpoint Algorith]] for line rasterization, but for circles.