---
tags:
  - PRL
aliases:
  - parallel matrix and vector
  - parallel matrix
  - parallel vector
sources:
  - "[[PRL_03_Matrixes_and_Vectors.pdf]]"
---
Parallel [[Matrix|matrix]] and [[Vector|vector]] algorithms are [[Parallel Algorithms|parallel algorithms]] and so inherit their analysis.
## Transposition
Converting a square matrix of size $n\times n$ with elements $a_{ij}$ into a square matrix of size $n\times n$ with elements $a_{ji}$. This operation can be thought of as rotating the matrix around its diagonal or turning columns into rows. This operation can be done with a non-square matrixes as well, which results in $n\times m$ turning into $m\times n$, but here we are going to focus on square ones.
The sequential solution is:
```
procedure TRANSPOSE(A)
for i=2 to n do
	for j=1 to i-1 do
		b = a[i,j]
		a[i,j] = a[j,i]
		a[j,i] = b
	endfor
endfor
```
The time complexity of this algorithm is $O(n^2)$.
### Grid Topology
Transposition can be done with a topology of a grid $n\times n$ for a matrix $n\times n$. Each processors has 3 registers:
- *A* contains $a_{ij}$ and $a_{ji}$ in the end.
- *B* contains value of the right (upper) neighbour.
- *C* contains value of the left (lower) neighbour.
The main idea is:
1. Each node in one half of the matrix (split by the diagonal) send its number to the one bordering the diagonal.
2. Bordering nodes send the numbers to the other side through the diagonal while receiving from the other side.
An analysis of this algorithm is:
- $t(n)=O(n^2)$
- $c(n)=O(n^3)$
- *Not optimal*
### Perfect Shuffle
The topology of this algorithm is a **perfect shuffle**. Only works over matrixes with $n\times n$ elements where $n=2^q$ for $q\in \mathbb{N}$. This means that overall $2^{q^2}=2^{2q}$ nodes and requires $2q$ bits for indexing. The main idea is:
1. Each processor sends the current element to the processor with the address one left shift over.
2. This is repeated for $2^{2q}-1$ cycles.
An analysis of this algorithm is:
- $t(n)=O(n^2)$
- $c(n)=O(\log n\times n^3)$
- *Not optimal*
### Shared Memory
Even for **EREW** the transposition is in constant time. The main idea is:
1. Each processor is assigned to a pair of values that will be swapped.
2. The processor independently swaps the elements without interfering with the other processors. 
- $t(n)=O(1)$
- $c(n)=O(n^2)$
- *Optimal*
## Matrix Multiplication
A multiplication of matrix $A$ with size $n\times m$ and $B$ with size $n\times k$ is the matrix $C$ with size $m\times k$, where the calculation is $c_{ij}=\sum_{s=1}^na_{is}\times b_{si}$. A basic sequential algorithm is:
```
procedure MATRIX MULT(A, B, C) 
for i=1 to m do 
	for j=1 to k do 
		cij = 0 
		for s=1 to n do 
			cij=cij + (ais * bsj) 
		endfor 
	endfor 
endfor
```
The complexity of this algorithm is $t(n)=O(n^3)$ and no algorithm has better time then $O(n^2)$.
### Shared Memory
A possible way of speeding up the algorithm is by doing each final cell in parallel, such as:
```
procedure MATRIX MULT(A, B, C) 
for i=1 to m do in parallel 
	for j=1 to k do in parallel 
		cij = 0 
		for s=1 to n do 
			cij=cij + (ais * bsj) 
		endfor 
	endfor 
endfor
```
### Grid
The topology is a grid of processors $n\times k$. The elements of a matrixes A and B are transferred into processors in the *first column* and *first row*. Each processor $P_{ij}$ contains final element $c_{ij}$.
```
Algoritmus procedure MESH MULT(A, B, C) 
for i=1 to m do in parallel 
	for j=1 to k do in parallel 
		cij = 0 
		while P(i,j) receives inputs a,b do 
			cij = cij + (a * b) 
			if i<m then 
				send b to P(i+1, j) 
			if j<k then 
				send a to P(i, j+1) 
		endwhile 
	endfor 
endfor
```
The analysis of this algorithm is:
- $t(n)=O(n)$
- $p(n)=O(n^2)$
- $c(n)=O(n^3)$
- *Not optimal*
## Matrix and Vector
Multiplication of a matrix $A$ with size $m\times n$ and vector $U$ with length $n$, where $v_{i}=\sum_{j=1}^na_{ji}\times u_{i}$.
### Linear
The topology is a *linear array* of $m$ processors, each contains one element of $v_{i}$. The algorithm then works in this way:
```
procedure LINEAR MV MULT 
for i=1 to m do in parallel 
	vi = 0 
	while Pi receives inputs a and u do 
		vi = vi + (a * u) 
		if i>1 then
			send u to Pi-1 
	endwhile 
endfor
```
The analysis of this algorithm is:
- $t(n)=O(n)$
- $p(n)=O(n)$
- $c(n)=O(n^2)$
- *Optimal*
### Tree
The topology of this algorithm is a *tree structure* with $n$ leaf nodes and $n-1$ non-leaf nodes. The basic idea is that the leaf nodes multiply while the non-leaf nodes add together. The algorithm is:
```
procedure TREE MV MULT(A, U V) 
do steps 1 and 2 in parallel 

(1) 
for i=1 to n do in parallel 
	for j=1 to m do 
		send ui*dij to parent 
	endfor 
endfor 

(2) 
for i=n+1 to 2n-1 do in parallel
	while Pi receives two inputs do 
		compute the sum 
		if i<2n-1 then 
			send result to parent 
		else 
			write result 
		endif 
	endwhile 
endfor
```
The analysis of this algorithm is:
- $t(n)=O(m)$
- $p(n)=O(n)$
- $c(n)=O(n\times m)$
- *Optimal*
