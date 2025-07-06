Is a [[Sorting]] algorithm.
## Princip
Sorts elements from **lowest priority** to the **highest priority** (from [[LSB]] to [[MSB]]) by placing them into boxes based on their class.
	An example of this could be with a set of `[12,35,81,44]`
	First the system would look at the lower priority part of the key, in this case it would look at the lower order in the number and sort the list in this was, which would result in `[81,12,44,35]`.
	Second the system would look at the next order and it values, which would result in: `[12,44,35,81]`.
## Properties
- Stable
- Unnatural
- Does on work in situ
- [[Time and Space Complexity|O(n * log n)]]