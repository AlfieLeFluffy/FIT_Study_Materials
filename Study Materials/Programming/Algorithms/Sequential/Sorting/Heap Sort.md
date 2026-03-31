Is a [[Sorting]] algorithm that uses a tree structure.
## Princip
Elements are arranged in a binary tree, where it applies for any (sub)tree that there is a relation of order between the parent and child elements. The tree does not have to binary but either way there are two requirements of the tree:
- All levels with the exception of the last one are filled.
- The last level is filled from left to the right.
	An example of this could be with a set of `[7,5,4,10,9]`
	In this example we create a heap out of the array by placing the element onto the tree from up to bottom and from left to the right. This should return `7 5,4 10,9` tree.
	We then reorder the tree to create a max heap (a heap with the maximum value at the top), which would turn the tree into `10 7,4 5,9`.
	With this tree we know that `10` is the highest number and so in the array version of this tree we place it at the back `[10,7,4,6,9] => [7,4,6,9,10]` and remove it from the tree (in the next iterations the `10` will no longer be accounted for).
	We once again create a max heap and do this until we run out of elements in the binary tree.
## Properties
- Unstable
- Unnatural
- Works in situ
- [[Time and Space Complexity|O(n * log n)]]