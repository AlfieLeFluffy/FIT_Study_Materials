---
tags:
  - PRL
aliases:
  - parallel sort
sources:
  - "[[PRL_02_Search_and_Sort.pdf]]"
---
Parallel sort algorithms are [[Parallel Algorithms|parallel algorithms]] and so inherit their analysis. Most of these algorithms are based on some version of a [[Parallel Networks|parallel network]], also known as topology.
## Types
The common types of parallel sorting algorithms share a lot of similarities with [[Sorting|sequential sorting]] algorithms. Some example can be:
- Comparing
	- Odd-Even Transposition
- Enumeration soring
	- On a grid
	- On a linear array
- Merging
	- Odd-Even Merge
	- Pipeline Merge
	- Merge-Splitting
- Minimum Extraction
- Division
	- Bucket Sort
	- Median Finding and Splitting
## Algorithms
A more detailed overview of these algorithms is:
### Odd-Even Transposition
The topology is a **linear array** of $n$ processors $p(n) = n$. The main idea is:
1. In the beginning each processor **p** contains one of unsorted values **y**.
2. In the first step each odd processors connects with its neighbour and compare values between each other. They swap values if a condition is met.
3. This is repeated until all values are sorted in **n** steps.
Analysis of this algorithm is:
- Each step uses a constant amount of steps.
- $t(n)=O(n)$ which is the best one can achieve with a linear topology
- $c(n)=t(n)\times p(n)=O(n^2)$ which is *not optimal*
### Grid Enumeration
The topology is a **two dimensional array** of $n\times n$ processors that are horizontally and vertically interconnected into a **tree structure**. The main idea is:
1. Each element is compared with every other using one row of processors.
2. The correct position of an element is $\text{RANK}(x_{i})=1+\text{amont of smaller elements}$.
3. Each element is inserted into the correct place.
Analysis of this algorithm is:
- $t(n)=O(\log n)$
- $c(n)=O(n^2\times \log n)$
- $p(n)=n^2$
- *Not optimal*
- Overall the algorithm is extremely quick (the best possible speed-up) but is also very costly
### Linear Enumeration
The topology is linearly interconnected $n$ nodes for sorting of a sequence with length $n$. Each node can hold two elements in its registers X and Y, RANK (C) and an output register Z can compare A and B and store the outcome into RANK. The main idea is:
1. Values are written into register X through the bus.
2. Values are moved to the register Y through a linear connection.
3. Values are are moved to register Z through the bus.
4. Each node compares values X and Y if available and possibly increments C.
5. If all value pair was compared then the value X is moved to Z based on C.
Analysis of the algorithm is:
- $t(n)=O(n)$
- $c(n)=O(n^2)$
- *Not optimal*
### Bucket Sort
The topology is a tree with $m$ leaf processors and $n=2^m$ that contains $2m-1$ processors, so $p(n)=(2\log n)-1$. Each leaf node processor contains $n/m$ elements and can sort them in an optimal sequence algorithm. The main idea is:
- Each non leaf processors can connect two ordered sequences in an optimal sequence algorithm.
Analysis of this algorithm is:
- $t(n)=O(n)$
- $c(n)=O(n\times \log n)$
- $p(n)=O(\log n)$
- *Optimal*
### Odd-Even Merge
The topology is a special case for merging. A unit CE orders two values on its inputs into its outputs. Connecting these units together will allow for merging of two ordered input sequences into one. To construct a common $n\times n$ block we need two blocks of $n/2\times n/2$, which is $N-1$ CE blocks. The idea is that:
1. Inputs are first checked in pairs in a single CE unit.
2. Two pairs are then checked by a $2\times 2$ unit.
3. This continues on until the highest unit compares all together.
Analysis of this algorithm is:
- $t(n)=O(m^2)=O(\log^2n)$
- $c(n)=O(n\times \log^4n)$
- *Not optimal*
### Pipeline Merge
The topology is a **linearly interconnected** nodes. Each node has two input [[Queue|queues]] and one outgoing. They merge together two ordered sequences of length $n$ into one sequence of length $2n$. The main idea is:
1. Each node takes in a number from the previous node and sorts into either one of the input queues.
2. Once it can compare two incoming queues then it releases through the one with the higher number.
3. This is repeated over and over through a chain of nodes until the end.
Analysis of this algorithm is:
- $t(n)=O(n)$
- $c(n)=O(n\times \log n)$
- *Optimal*
### Median Finding and Splitting
Uses the same architecture as Bucket sort. each processor with $m$ leaves, $n=2^m$, $m=\log n$. Processor on the level $i$ processes $n/2^i$ elements. Each leaf node knowns how to do an optimal sequence sort. Something new that the bucket sort does not know how to do is that each non-leaf processor knows how to find the median in an optimal time. The basic idea is:
1. Root loads sequence S, finds median M, splits S by M and sends sequences to its children.
2. Each non-leaf node finds the median M for the incoming sequence, splits the sequence by M and sends it to its children.
3. Leaf nodes sort the incoming sequences.
4. The output are the sequences of each leaf node read in order (from left to right).
Analysis of this algorithm is:
- $t(n)=O(n)$
- $c(n)=O(n\times \log n)$
- *Optimal*