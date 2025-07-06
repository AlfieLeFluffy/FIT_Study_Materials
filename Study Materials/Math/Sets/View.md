A view is a rule (regulation) by which elements of set **X** are connected to at **maximum one** element of set **Y**. We can call this a view of set **X** into set **Y**. Elements of **X** are called **patterns** and elements of set **Y** are called **picture**. This is similar to functions in which x has only on value of y. Views are a special kind of [[Relation#Binary Relation|Binary Relation]] in which each pattern has only one picture.
## Types
### Basic Views
#### Injective (Simple) View
Each element of set **Y** has at least one element of **X** mapped onto it.
#### Surjective View
Each element of set **X** has a relation with an element of set **Y**. (This means that **Y** elements can have multiple patterns).
#### Bijective (Shared Unique) View
Each element of set **X** has a relation with one element of set **Y**, which only has one pattern. This means that for each element **x** there is exactly one element **y**. It is both Injective and Surjective view at once.
### Special Views
#### Inverse View
Inverse view for some view **f: A -> B** is a view that maps elements of set **B** to elements of set **A**. This means that the pictures are mapped onto the views. For this to work the original view **f** must be **injective**.
#### Supremum and Maximum
If **A** is a non-empty set with a ceiling (has an upper border, is not infinite) of **R** (real numbers), then number **sup(A)** is called a supremum of set **A** if it is the **smallest upper border** (bolt) of set **A**. **Sup(A)** has to be bigger or equal to all elements of set **A**, but does not have to the the maximum. For example, interval **X = (2, 3)** has **supremum** of **3** (sup(X) = 3), but it does not have a maximum, because it is an open interval. **Y = (2,3>** has a supremum of 3 and it is its maximum.
#### Infimum and Minimum
If **A** is a non-empty set with a floor (has an lower border, is not infinite) of **R** (real numbers), then number **inf(A)** is called a infimum of set **A** if it is the **biggest lower border** (bolt) of set **A**. **Inf(A)** has to be smaller or equal to all elements of set **A**, but does not have to the the minimum. For example, interval **X = (2, 3)** has **infimum** of **2** (sup(X) = 2), but it does not have a minimum, because it is an open interval. **Y = <2,3)** has a supremum of 2 and it is its maximum.
### Union (Svaz)
Union is **ordered set**, which is expanded with a property that for **any two elements** from a given union must have a **supremum** and **infimum** that lie in the union.
### Group
A group is a set **G** in combination with binary operations. For example for operation **+** it must apply that:
- Operation **+** must be over the set **G** closed.
- Operation **+** must be over the set **G** associative.
- There exists a **neutral element e** that is part of the set **e ∈ G** that in any operation with **+** returns the unaltered other parameter.
- There exist **inverse elements** that for each element **a ∈ G** exists element **b ∈ G** that in operation together **a + b = b + a = e**, where **e** is the neutral element.