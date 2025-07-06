Is a Selection [[Sorting]] algorithm.
## Princip
Sorts elements by comparing the current value and the next value. If these values are reverse (the one of the left is higher then the one on the right) it switches them around. Either way it takes the next value and uses it as the new current one. The algorithm goes through the list in cycles until it passes through without switching a single pair.
	An example of this could be with a set of `[7,5,4,10,9]`
	First the algorithm takes the `7` and the `5`, checks them and switches their places resulting in `[5,7,4,10,9]`.
	The algorithm then continues for `7` and `4`, resulting in `[5,4,7,10,9]`.
	This continues until there were no switches made
## Properties
- Stable
- Natural
- Works in situ
- [[Time and Space Complexity|O(n^2)]]