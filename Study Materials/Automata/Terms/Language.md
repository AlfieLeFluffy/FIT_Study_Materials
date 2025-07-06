If **Σ\*** is a [[Set]] of all possible [[Language#String|strings]] over [[Alphabet|alphabet]] **Σ**, then each subset **L ⊆ Σ\*** is a language over the alphabet **Σ**. These subsets are then sets of strings made up of the alphabet. The **amount of words** of a language is its cardinality. 

## Types
- A **finite** language has an ending (countable) amount of strings is finite.
- An **infinite** language is the opposite, where the amount of strings is uncountable.
## Operations
There are several operations with languages that follow the same rules as working with sets:
- **Unification**
- **Intersection**
- **Difference**
- **Complement**
- **Concatenate** is an operation in which languages **L1** and **L2** are languages under the same alphabet **Σ** where elements of one language are connected with the elements of another **L = L1|L2 = {xy: x ∈ L1, y ∈ L2}**. An empty language cannot be concatenate, but a language containing an empty string can be.
	**L = L1|L2 = {0, 1}.{2, 3} = {02, 03, 12, 13}**
- **Reverse** is an operation in which language **L** of alphabet **Σ** where elements have their symbol order reversed. It is symbolized by **reverse(L) = {reverse(x):  x ∈ L}**.
	**reverse({01, 02, 20, 21}) = {10, 20, 20, 21}**
