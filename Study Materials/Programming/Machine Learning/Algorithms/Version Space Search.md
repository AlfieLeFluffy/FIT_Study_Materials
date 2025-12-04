**Version Space Search** is a set of methods that learn their terms/hypothesis based on **positive** and **negative** example. During studying the algorithm searches for a **description** of a said **term/object/hypothesis**, which **includes all positive examples** and **excludes all negative examples** from the training data. The training data then must have examples that are evaluated as **positive** and **negative** and usually contains attributes by which the algorithm decides. An example of such data can be:
```
1. object(small, red, ball) - positive
2. object(small blue, box) - negative
3. object(big, red, ball) - positive
4. object(big, red, box) - negative
5. object(small, blue, ball) - positive
6. object(small, white, box) - negative
```
### Specific to General Search Algorithm
A method learns the search space from the specific to a general. Otherwise said the **positive examples** are in the outcome more general, they are adding more correct solutions. The negative examples on the other hand reduce (remove examples that would incorrectly identify a wrong object).
#### Steps
1. Create two sets **S** (specific) and **N** (negative).
2. Store into the set **S** the first positive example. For each other example **p** from the training set do:
	1. If **p is positive**, then for each **s in S**:
		1. If **s** and is not able to be unified with **p** (**s** is more general then **p** and **p** is under the set of element that can be constructed from **s**) with example **p**, then replace it with a more **specific generalization** in a way it can be unified with **p**.
		2. Remove from **S** all terms **s**, that are more general then other terms in **S**.
		3. Removes from **S** all terms **s** that can be unified with some term in **N**.
	2. if **p is negative** then:
		1. Remove from **S** all terms **s** that can be unified with the example **p**.
		2. Add **p** into **N**.
### General to Specific
A method learns from the search space from a general understanding to a specific one. Otherwise said with **negative examples** the general solution become **more specific**, because the solution is concretized so it would not fit the **negative example**. **Positive examples** then remove those **solutions**, which are not able to be unified with the **positive example**.
#### Steps
1. Create two sets **G** (general) and **P** (positive). Into the **G** save the most general term (all parameters are variables).
2. For each example **p** from the training set do:
	1. If **p is negative** then for each term **g** in **G**:
		1. If **g** can be unified with the example then replace it with the most general term that cannot be unified with **p**.
		2. Remove from **G** all terms **g** that more specific then other terms in **G**.
		3. Remove from **G** all terms **g** that cannot be unified with some of the examples in **P**.
	2. If **p is positive** then:
		1. Remove all terms **g** from **G** that cannot be unified with example **p**.
		2. Add **p** into **P**.
### Candidate Elimination
Combines both previous algorithms.
#### Steps
1. Create two set **S** (specific) and **G** (general) and store the most general term in **G** and store a first positive example into **S**.
2. For each example **p** from the training set do:
	1. If **p is positive**:
		1. Remove all elements **g** from **G** that can be unified with **p**.
		2. For each term **s** from **S**:
			1. If **p** cannot be unified with **s** then a more specific generalization so it can be unified with **p**.
			2. Remove from **S** all terms **s** that are more general then other terms in **S**.
			3. Remove from **S** all terms **s** that are not more specific then then terms in **G**.
	2. If **p is negative**:
		1. Remove from **S** terms **s** that can be unified with **p**.
		2. For each term **g** in **G**:
			1. If **g** can be unified with **p** then replace it with the most **general specialization** that cannot be unified with **p**.
			2. Remove **g** from **G** that are more specific then other terms in **G**.
			3. Remove **g** from **G** that are more general then terms in **S**.
If **G = S** and both sets contain **only one term** then that is the outcome of the learning.
#### S and G
The reason and relation between sets **S** and **G** is that each term that would be more general then some term in **G** would contain some **negative examples** and each term that would be **more specific** then some term in **S** would exclude **some positive examples**. 