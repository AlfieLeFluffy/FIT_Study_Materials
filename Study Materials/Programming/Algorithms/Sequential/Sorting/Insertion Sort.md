Is a Insertion [[Sorting]] algorithm.
## Princip
Works same as ordering card in a hand. Selects an unordered element and place it in a place it it belongs to. 
1. For this we create an ordered side on the left and unordered side on the right of the set. The ordered side will have one element which is the first element in the set.
2. We select the first element from the unordered side.
3. In the ordered side we find a place it belongs (where it is bigger then the one on the left, but smaller then the one on the right).
4. Shift all elements to the right of the found position.
5. Insert the element.
6. Continue until the list is empty.
	An example of this could be with a set of `[7,5,4,10,9]`
	First the element takes the `7` as the ordered side and the rest as not ordered so we get `[7|5,4,10,9]`.
	We take the first element from the unordered side like `5` and find a place for it before the `7`.
	We take out the element `5` and shift the entire list to the right resulting in `[_,7|4,10,9]`.
	We place the element `5` in the place we found it `[5,7|4,10,9]` and repeat until we no longer have unsorted elements.
### Bubble-Insert Sort
Modification that uses bubble sort while comparing to shift element right in exchange for the selected element.
### Binary-Insert Sort
Modification that uses binary search (halving of intervals) to find the place the value should be inserted into.
## Properties
- Stable
- Natural
- Works in situ
- [[Time and Space Complexity|O(n^2)]]