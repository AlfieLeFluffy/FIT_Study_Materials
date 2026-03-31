Is a Partition [[Sorting]] algorithm.
## Princip
Works on the principal of **divide and conquer**. It is one of the quicker algorithms for sorting, but its speed is non-deterministical. 
1. Divide the set into two subsets.
	1. First one contains elements smaller/bigger then the median.
	2. Second one contains elements bigger/smaller then the median.
2. These subsets once again subdivide into two sets of similarly ordered elements.
3. End once the set only contains 1 element.
The shifting of elements based on the median is done through:
 - The walk is done from the left and the right at the same time.
 - From the left we are looking for elements bigger then the median and from the right we are looking for elements that are smaller.
 - Once both sides find an element they switch places.
 - We end the walk once we find a pair that has crossed into the other side (got inverted).
 Median should be an element which is smaller then half the element, but bigger then half the elements. Finding a median can be quite difficult so we can substitute with a pseudo median, which can be a random value within the set.  
	An example of this could be with a set of `[7,9,4,10,5]`
	First we select a pseudo median of `7`.
	Then we check if `9` is smaller or bigger then `7`, it is bigger, so we have a bigger value from the left.
	Then we checks if `5` is smaller of bigger then `7`, it is smaller and due to us having both left and right values found we switch them, so we get `[7,5,4,10,9]`.
	We do this until the searching index cross over each other and then we subdivide the set in the place they met into set smaller then `7` `[5,4]` and bigger or equal to `7` `[7,10,9]` and do the same thing again until we finish sorting.
## Properties
- Unstable
- Unnatural
- Works in situ
- [[Time and Space Complexity|O(n * log n) - O(n^2)]]