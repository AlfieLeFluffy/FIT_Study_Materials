---
tags:
  - PRL
aliases:
  - reduction computer
  - reduction computers
sources:
  - "[[PRL_01_Parallel_Architectures.pdf]]"
---
A reduction computer uses [[Functional Programming|function programming]] and is based on reduction of expressions. A reduction in this context means replacing part of an expression by its value. An example of an expression can $x*y+(x-y)$, in LISP that would be $(+ (* x y)(-yxy))$ and in a reduction computer it would be divided into sequences $+<(*<xy>)(-<xy>)>$.
## Reduction Tree
A reduction expression can be represented by a reduction [[Tree|tree]], where non-leaf nodes are processors and communication nodes and leaf nodes are memory.
## Reduction Languages
An example of an reduction language is ALICE, which is based upon a recursively enumerable functions ([[Functional Programming|function programming]]).