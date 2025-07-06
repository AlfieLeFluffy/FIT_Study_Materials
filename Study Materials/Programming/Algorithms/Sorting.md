- **Sorting** elements in a unsorted sets (lists) is **arranging elements into classes** based on values of a **given attributes** (keys). Between each class be there does not have to be defined a relation of ordering. Commonly we use ordering to sort classes.
- **Ordering** (sequencing) is arranging of element based on a **linear ordering relation** over keys. This terms is not used often.
- **Merging** is creating a set of sorted elements by unification of several sets of elements of the same type that are already ordered. An example of this **Merge Sort**.
## Properties
There are two properties that are used for selecting a algorithm based on implementation criteria:
- **Stability** refers to if elements of the same value in the key variable will be kept in the same order in the ordered set as they were in the unordered one.
	- An example could be for this set `[1,2',2'',3,2''']` a stable solution is `[1,2',2'',2''',3]` and an unstable is `[1,2''',2',2'',3]`.
- **Naturalness** refers to when an algorithm meets two conditions. If these condition are not met then the algorithm is an unnatural algorithm. These conditions are:
	- Time to sort a **randomly ordered set** is greater then sorting an already **ordered set**.
	- Time to sort a **set ordered in reverse** is greater then sorting an already **randomly ordered set**.
## Types
**By ordering princip**:
- **Selection** - moving **maximum** and **minimum** values to an output set. These are for example: **Selection** sort, **Bubble** sort and their modifications like **Ripple**, **Shaker**, **Shuttle**.
- **Insertion** - inserts elements into an ordered output set. This is for example **Insertion** sort.
- **Partition** - divides elements into subsets in a way that elements on are smaller then elements of the other. These are for example **Quick** sort and **Shell** sort.
- **Merging** - orders two ordered sets into one. This is for example as **Merge** sort.
**By processor type**:
- **Serial** - one processor that only does one operation at one moment.
- **Parallel** - can do several operations at one moment.
**By memory access**:
- **Direct** (random) access - the method has internal ordering such as ordering arrays.
- **Sequential** access - the method has external ordering such as ordering file or lists.
## Sorting Algorithms
![[Radix Sort (Classes)]]

![[Selection Sort]]

![[Bubble Sort]]

![[Heap Sort]]

![[Insertion Sort]]

![[Quick Sort]]

![[Shell Sort]]

![[Merge Sort]]
## Ordering Using Multiple Keys
Can be achieved by sorting the array multiple times using different keys same as [[Radix Sort (Classes)]]. It must be followed that:
- Sorting must be done from the lower priority key to the highest.
- We must use stable algorithms.
Another way to achieve this would be to do only one ordering, but using all the keys at once, something like sorting dates by giving them the format YYYYMMDD, which if sorted would give the accurate order, even though multiple keys were used.
## Ordering Without Moving Elements
It is recommended for sets that deal with big elements, where moving around the actually elements would be costly and so we create another representative set of and sort that one, in which the sorted elements will point to the elements in the original sets.