---
tags:
  - IAL
  - IUS
aliases:
  - AND/OR Graph
  - AND/OR graph
  - and/or graph
---
AND/OR graph is a special case of [[Graph|graphs]] used in [[Task|tasks]], [[Task Decomposition|decomposition of tasks]] and [[Game Theory Methods]]. Normal [[Graph Algorithms|graph algorithms]] do not work with these kinds of graphs of their special rules regarding choice. Vertexes (states) in these graphs are called **problems**, **sub-problems** or nodes.
## Problem Types
As the name suggest there are two kinds of **problems**:
### OR Node
An OR problem is solvable if at least one of its sub-problems is solvable.
### AND Node
An AND problem is only solvable is all of its sub-problems are solvable.
## Conversion
A general AND/OR graph can be converted into a AND/OR graph in which there are only AND or OR nodes on each layer. 