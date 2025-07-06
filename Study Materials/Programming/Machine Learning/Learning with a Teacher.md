It is based upon the principle that with **each step** of the learning process the **required response is known**, so the system is immediately informed of the **current evaluation of the last action**. This learning is done on a set of example **T**, where each example is represented by a **set of input variables** (input vector) and a **set of correct or required output values** (output vector).
The set of learning data is commonly divided into **two or three subsets**. The first subset is the **training data** (can be 80%), the second is testing (can be 20%) and the last one can be used to tweak the final parameters.
Methods with teachers work with vectors, that have symbolic values (numeric values are also symbolic) and are based on the assumption that each hypothesis, that satisfies a big enough set of training data, will be satisfying even to unknown examples.
## Decision Tree Building
A decision tree is used to classify objects based on the values of its attributes. They are created with a known set of examples and are used in datamining from databases.
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
## Version Space Search
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
## Pattern Recognition and Classification
For recognition of pattern there exist several algorithms, that work with one of the next description of the objects:
- **Symptomatic Description** (vectors of numeric symptoms) use static information about image symptoms contained in the training data set. This can be through of as a list of information containing things like number of segments, horizontal segments, vertical segments, diagonal segments, etc.
- **Structural**/**Syntactic** (structural element or primitives) use relations between image symptoms of the recognized objects. This can be through of as a graph of nodes each corresponding to a primitive such as horizontal and vertical lines.
A necessary assumption is that successful recognition is a selection of relevant symptoms or primitiv.
### Symptom Recognition
A sign recognition works with:
- **n-dimensional number vectors** of signs that describe the recognized object
- **Set of classes** into which the objects can be classed into.
- **Training set** comprised of doubles of n-dimensional number vectors and a class into which the object belongs.
The goal is the classifications of any vector of symptoms into one of the classes. These methods are based on the assumption that images of objects or phenomena classed into the same class create in n-dimensional space **groups**. These groups can be from each other easily distinguished (**separable**) or they can intersect one another (**inseparable**). Systems that learn and then recognize new objects are called **classificatory**.
#### Dichotomie
It is classification into **one of two classes**. In practice **dichotomie** is quite common, generally it is classification into **N** classes, which is based on finding of **curves/areas/k-polynoms** that create images of each class and separate one from the another. This can be ensured by a **discrimination** function (for each class one) that can evaluate an image. An image is then classed into a class that has the highest evaluation. In dichotomie we can use just one function (two of them that we subtract) and the classification is then based on the sign.
#### Etalony
It uses center of gravity of image clusters. An image is classed to which **etalone** it is closest to. This method still uses a discrimination functions.
#### Recognition of Images Represented by an Inseparable Classes
In case of inseparable classes it cannot be determined if an image goes into class **r**, but it can be said that the image goes into a class with probability **P(r|x)**. The goal of the training algorithm is to find such classificators that will class images with the highest probability, in other words they try to minimize loss that is create by classification into an incorrect class. For this a loss [[Matrix]] is used and a loss for a correct classification is 0 and for incorrect it is 1. Based on this the matrix is simplified.
### Structural Recognition
Structural recognition does classification of images using primitives. There exist two basic ways for structural classification:
- Using **Grammar** (Syntactic Recognition)
- Using **Comparision with Patterns** that are saved in a database.
**Syntactic** recognition classes object into R classes based on an **syntactic analysis**.
#### Freeman Chain Code
This code is used to create a structural description of an objects outline. The primitive describing the objects outline are directions to the neighbours. Problem with this is their rotation and starting position, but they can be eliminated:
- **Rotation** can be solved by using relative (differential) code, that instead of neighbour directions uses **ratio/difference in rotation** between each neighbour. 
- **Starting Position** can be solved through rotating the number around until its the biggest number possible.
The final **shape number** is then invariant against transposition, rotation and starting point, but it is still dependent on its size.