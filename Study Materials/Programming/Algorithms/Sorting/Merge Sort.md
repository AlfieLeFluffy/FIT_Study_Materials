Is a Merge [[Sorting]] algorithm.
## Princip
Works on the principal of **divide and conquer**. At first it will divide the set into 2 subsets, which will continue down until it gets sets of 1 element. Then it will merge these sets together, picking lowest values from each until they are merged.
	An example of this could be with a set of `[7,5,4,10,9,8]`.
	We divide the set into `[7,5,4]` and `[10,9,8]`.
	We divide the first set into `[7,5]` and `[4]`.
	We divide the first set into `[7]` and `[5]`.
	We merge these two sets back together first taking the `5` and then the `7` so we get `[5,7]`.
	We merge these sets `[5,7]` and `[4]`, first taking the `4`, then the `5`, then the `7`, so we get `[4,5,7]`.
	W continues this way dividing and merging until we merge back the entire set.
## Properties
- Stable
- Does not have to be natural
- Works in situ, but has more [[Time and Space Complexity|Space Complexity]]
- [[Time and Space Complexity|O(n * log n)]]