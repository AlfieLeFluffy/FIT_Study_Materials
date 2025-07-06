Is a Selection [[Sorting]] algorithm.
## Princip
Sorts elements by finding extreme element of a set (highest/lowest) and moving to the beginning or the end of the set. The algorithm then starts searching from the next value (the value after or before the one just place).
	An example of this could be with a set of `[7,5,4,10,9]`
	First the element takes the `7` as the newest lowest number.
	Second it tests the lowest with the new one of `5` and changes it to the new lowest.
	This happens again with the `4`.
	The algorithm does not find a new lowest number and reaches the end.
	The algorithm places the `4` at the beginning of the set, resulting in a set `[4,7,5,10,9]`.
	The algorithm starts again from the second position which is once again `7`.
## Properties
- Unstable
- Should be Natural
- Works in situ
- [[Time and Space Complexity|O(n^2)]]