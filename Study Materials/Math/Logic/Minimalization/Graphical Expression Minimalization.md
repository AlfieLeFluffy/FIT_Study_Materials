Graphical logic expression minimalization uses either tables or graphs to minimalize logic expressions. These methods are easier for a human to implement, especially with complex expressions.
## Karnaugh Maps
These maps use [[Gray Code]] in a way that each cell within the map has neighbours that are only one bit in difference. Columns or rows in which a variable (x, y, z) are highlighted for ease of use.
![[Gray Code]]
After a map is created it is filled with 1 and 0 in their respective places. Once both the map and the values are setup then there are two ways to solve them, each representing either [[Product of Sums (CNF)]] or [[Sum of Products (DNF)]].
### Solving for Disjunctive Form
Solves the map so in the end the form is [[Sum of Products (DNF)]].
Log. 1s (or X) in the map can be formed into groups that are power of 2. This can also be done over the edges and corners.
	Ones in all four corners can be grouped together.
After that for each group it must be decided if a variable is part of the final group's term. The terms are the result of a product so multiplication between them.
- If the variable has both a 0 and 1 bit values in the group's space (row/column) then it won't be part of the term
- If the variable has only a 1 bit values in the group's space (row/column) then it will be there as a variable **without** a negation.
- If the variable has only a 0 bit values in the group's space (row/column) then it will be there as a variable **with** a negation.
As a final step all terms of expression are added together.
### Solving for Conjunctive Form
Solves the map so in the end the form is [[Product of Sums (CNF)]].
Log. 0s (or X) in the map can be formed into groups that are power of 2. This can also be done over the edges and corners.
	Zeros in all four corners can be grouped together.
After that for each group it must be decided if a variable is part of the final group's term. The terms are the result of a sum so addition between them.
- If the variable has both a 0 and 1 bit values in the group's space (row/column) then it won't be part of the term
- If the variable has only a 1 bit values in the group's space (row/column) then it will be there as a variable **with** negation.
- If the variable has only a 0 bit values in the group's space (row/column) then it will be there as a variable **without** a negation.
As a final step all terms of expression are multiplied together.

