Is a Partition [[Sorting]] algorithm.
## Princip
Works on the principal of **divide and conquer**. It creates sequences of elements that are then went through with [[Bubble Sort]]. 
1. First the sets is divided into subsets of **2** with elements that furthest away from each other.
2. These sets are sorted.
3. The set is divided into subsets of **4** with elements that furthest away from each other.
4. These sets are sorted and so this goes up until it finally sorts the entire set.
	An example of this could be with a set of `[7,5,4,10,9,8]`
	We create subsets `[7,10]`, `[5,9]` and `[4,9]`.
	These subsets are ordered and put back together in the same order as the original places of these elements were and continue.
## Properties
- Unstable
- Should be matural
- Works in situ
- [[Time and Space Complexity|O(n * log(n)^2) - O(n^(3/2))]]