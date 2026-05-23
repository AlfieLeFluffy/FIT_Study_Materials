---
tags:
  - IOS
aliases:
  - b+ tree
  - B+ tree
sources:
---
Today these [[Tree|trees]] are the most commonly used way of storing files on a disk (can include modifications). It solves the **issue of sequential and random access** to the data. The effectivity of B+ trees is based on its time complexity of [[Time and Space Complexity|O(n * log n)]] when searching through the tree.
## Tree Structure
- **Internal Node** is made up of **K** amount of keys (identification of blocks, their sequential number) and **K + 1** links to nodes of lower level. The keys in a node are **ordered sequentially** (from lowest to highest) and the keys next to each other define the interval of keys between them. These interval are **closed from the left** and **open from the right** meaning that on an interval key **i** to key **i+n** if we are looking for key **i** then it is in this interval. Because the keys are ordered the searching can also be done through **halving of the interval**.
- **External Node** (or leave nodes) have the same structure as the **internal nodes**, but instead of pointing to another level of the tree **they point at the data blocks**. The last link in this block also link to the next external (leave) node in sequence, which makes it easy to continue on sequentially reading the data blocks if needed. The values of the data block keys can be affected by fragmentation, which requires all of the keys to be written down, otherwise it might cause issues.
## Properties
- **B+ Trees** are height balanced and it applies to them that:
	- **Fullness Limit** for a node with **m** links (so keys from 1 to m-1):
		- Sole root from 1 to m-1
		- Root from 2 to m
		- Internal node from m/2 to m
		- External node from m/2-1 to m-1
	- **Insertion** is done on the **leave level** and if the node overflows then the node splits and can even split higher level nodes up until the root is split. In case the root split the entire tree grows in level.
	- **Deletion** is also done on the **leave level** and if the minimal rule for fullness is violated then the tree either consolidates the remaining entries into other nodes or it unification of two node into one that does not violate the fullness rule. This can also lead to unification of higher nodes up until a new root is formed through unification, in which case the tree goes down a level.