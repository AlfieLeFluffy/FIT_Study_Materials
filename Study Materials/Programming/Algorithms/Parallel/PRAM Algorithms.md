---
tags:
  - PRL
aliases:
  - PRAM algorithms
sources:
  - "[[PRL_05_PRAM.pdf]]"
  - https://www.youtube.com/watch?v=4mSQXGi0zSk
---
These parallel algorithm are based on the [[Parallel Random Access Machine|PRAM]] architecture.
## Characteristics
Most of the characteristics are based on both [[Parallel Random Access Machine|PRAM]] architecture characteristics and [[Parallel Algorithms|parallel algorithms]].
## Algorithms
### Broadcast
Broadcast takes a value that is saved in memory and spreads it between $N$ processors. Using the different PRAM architectures:
- For CREW and CRCW the solution is trivial in constant time.
- For EREW it is necessary to simulate concurrent reading.
The basic idea follows the structure:
1. $P_{1}$ reads $D$ and makes it available to $P_{2}$
2. $P_{1}$ and $P_{2}$ make the value available to $P_{3},P_{4}$
3. Continues with exponential growth
The analysis of this algorithm is:
- SEQ: $t(n)=O(n)$
- EREW: $t(n)=O(\log n)$
- CREW, CRCW: $t(n)=O(c)$
### Prefix Sum
Also known as **all-prefix-sum**, **allsums** or **scan**, it is one of the cornerstones of parallel algorithms. By definition prefix sum is an operation of which the input is binary associative operator $\oplus$ and an ordered sequence of elements $[a_{0},a_{1},\dots,a_{n-1}]$ and returns $[a_{0}, (a_{0}\oplus a_{1}),\dots,(a_{0}\oplus a_{1}\oplus\dots a_{n-1}\oplus)]$.
For example if the $\oplus$ is just normal sum and the sequence is $[3,1,7,0,4]$ then the result is $[3,4,11,11,15]$.
There are many use cases for this operation, such as:
- Evaluating polynomials
- Sum of binary numbers in HW
- Lexical string comparison
- Lexical analysis
- Implementation of [[Radix Sort (Classes)]], [[Quick Sort]]
- Cancelling flagged elements in an array
- Searching for [[Regular Expressions]] (grep)
- Implementation of some [[Tree]] operations
- Highlighting components in 2D images
It is implemented in many libraries and programs under different names, such as:
- MPI: MPI_scan
- MATLAB: y=cumsum(x)
Any associative operator can be used, such as:
- Sum
- Product
- Max
- Min
- AND
- OR
- XOR
- Concat
- MatMul
Sequential solution is:
```
procedure allsums (Out, In) 
i=0 
sum = In[0] 
while i<length do 
	i = i+1 
	sum = sum + In[i] 
	Out[i] = sum 
endwhile
```
This has the time complexity of $t(n)=O(n)$.
