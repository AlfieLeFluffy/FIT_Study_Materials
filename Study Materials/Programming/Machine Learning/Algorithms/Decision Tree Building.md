---
tags:
  - IZU
  - SUI
aliases:
  - decision tree building
  - decision tree
---
A **decision tree** is used to classify objects based on the values of its attributes. They are created with a known set of examples and are used in datamining from databases.
### Decision Tree Algorithm
It is a basic algorithm for building a decision tree. It has two input parameters:
- **Set of Example MP**
- **Set of Condition Attributes MA**
#### Steps
1. If **all elements** of a set examples **MP** are part of the same class, return a **leave node** signified by their class, otherwise continue.
2. If the set of attributes **MA** is empty, return a **leave node** signified by a **disjunction** of all classes into which belong the elements of examples set **MP**, otherwise continue.
3. Select an attribute **Ai**, remove it from the set of attributes **MA**, and make it the root of the **current tree**. The **MA-i** is the set of attributes **MA** without the attribute **Ai**.
4. For each value of **Hji** of the selected attribute **Ai**:
	1. Create a new branch signified by value **Hji**.
	2. Recursively call the algorithm with parameters **MPji** and **MA-i**, where **MPji** is a subset of all elements **MP**, which have the value **Hji** of the attribute **Ai**.
	3. Connect the returned tree (node) into this branch.
In other words, it creates the **tree based on the decision parameter**. The depth of the tree is based on if some of the attributes can be ignored, because no matter its value, the outcome from the training data is the same.
#### Evaluation
The algorithm is simple, but has a crucial issue, which is selection of the attribute **Ai** in step 3. Inappropriate selection can lead to deep and non-effective decision trees, even through an optimal tree can be rather simple.
### ID3 Algorithm
It is a modification of the **Decision Tree Algorithm** that solve the issue of selection of the attribute **Ai** in step 3. Selection of the attribute is not random, but it is done in a way to **maximalize information gain**. This means that it select attributes that will have the greatest impact on the **decision**. Another way of thinking about it is that the sets that get created by division by that attribute will have the **smallest entropy** (it contains elements that fall under one outcome). If a subset contains element of the same outcome, then the overall entropy of the set is 0. If on the other hand the set contains elements all of different outcomes then the entropy will be the highest. We select attributes that will cause the lowest amount of entropy.
#### Calculation
To calculate an entropy of a set we can use a general idea where:
$$
E = - \frac{g}{c} \log_{2}\left( \frac{g}{c} \right)
$$
Where:
- **E** is the entropy for one possible value
- **g** is the of elements that share one outcome
- **c** is the complete number of elements in this subset
This can be calculated for each possible outcome elements in a subset share, these values then can be added together and we have an entropy value for a given subset. From these entropy values we can then created their weighted sum (each by the amount of elements they contain) and this is the overall entropy value for a given possible decision attribute.