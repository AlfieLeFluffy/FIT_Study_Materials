---
tags:
  - PRL
aliases:
  - parallel search
sources:
  - "[[PRL_02_Search_and_Sort.pdf]]"
---
Parallel search algorithms are [[Parallel Algorithms|parallel algorithms]] and so inherit their analysis.
## Characteristics
Some basic characteristics are:
- **Input**: sequence $X=\{ x_{1},x_{2},\dots, x_{n} \}$
- **Task**: finding $x=x_{k}$ and its position
- Optimal sequence algorithm has complexity:
	- **Unordered**: $t(n) = O(n)$, $c(n) = O(n)$
	- **Ordered** (binary): $t(n)=O(\log n)$, $c(n)=O(\log n)$
## Algorithms
There are many applications for parallel searching and most of them are specialized versions of sequential algorithms. Not all sequential algorithms benefit from parallelization, but examples of those that can are:
### Searching Unordered
Possible algorithm:
```
procedura SEARCH(S, x, k) { sequence, element, result} 
1. 
for i = 1 to N do in parallel 
	read x 
endfor 

2. 
for i = 1 to N do in parallel 
	Si = {s(i-1).(n/N)+1, s(i-1).(n/N)+2, ..., si.(n/N)} 
	SEQUENTIAL_SEARCH (Si, x, ki) ## paralell Search calls SEQUENTAL Search 
endfor 

3. 
for i = 1 to N do in parallel 
	if 
		ki > 0 then k = ki 
	endif 
endfor
```
An analysis of the algorithm:
- **EREW**
	1. $O(\log n)$
	2. $O(n/N)$
	3. $O(\log N)$
	- $t(n) = O(\log N+n/N)$
	- $c(n) = O(N\log N+n)$
	- In phase 1. each node much know the searched element.
- **CREW**
	1. $O(1)$
	2. $O(n / N)$
	3. $O(\log N)$
	- $t(n) = O(\log N+n/N)$
	- $c(n) = O(N\log N+n)$
- **CRCW**
	1. $O(1)$
	2. $O(n / N)$
	3. $O(\log N)$
	- $t(n) = O(n / N)$
	- $c(n) = O(n)$ 
	- *Optimal*
### Searching Ordered
Searching in a ordered sequence with a **CREW** and $N$ processors. Algorithm princip:
1. While using binary search, it is possible to distinguish in which half the element is using one processor.
2. With $N$ processors it is possible to do $N+1$ searches. In one step we can find out in which part the element is.
3. If the pointers of two following explored elements are different (left, right) then the range of the search is adjusted.
This search requires $g=[\log(n+1)/\log(N+1)]$ steps, where $g$ can also be expressed as the the smallest number such that $n\leq(N+1)^g-1$
For this algorithm the **CREW PRAM** is necessary with analysis:
- $t(n) = O(\log(n+1)/\log(N+1)) = O(\log_{N+1}(n+1))$
- $c(n) = O(N\times\log(n+1))$
- *Not optimal*
### Searching Tree
When searching trees it is assumed the [[Tree|tree]] is binary tree and there is $2n+1$ processors. The main princip is:
1. The tree root loads the searched value and sends it to its children and they send it to their children, rinse and repeat until they get to the leaf nodes.
2. Leaves contain the element we are looking for and the result is either 0 or 1.
3. All results are sent to the root, each non-leaf node calculates a logical sum of child results and sends results higher.
4. Root receives either 0 for not found or 1 for found.
The analysis is:
- $t(n) = O(\log(n))$
- $c(n) = O(n\times\log(n))$
- *Not optimal*
### Parallel Splitting
The task is to split a [[Set|set]] such that:
- *Input*: sequence of number **S** a number **m**
- *Output*: three sequences **L**, **E** and **G** such that:
	- $L=\{ s_{i} \in S: s_{i} <m\}$
	- $E=\{ s_{i} \in S: s_{i} =m\}$
	- $G=\{ s_{i} \in S: s_{i} >m\}$
The time complexity of a sequence solution is $O(n)$. For the parallel solution we have $N$ processors that divide the sequence **S** into subsequence **Si** of length $n/N$. The psuedo-code could be:
```
1. m is sent to each of N processors
2. each processors Pi segments the sequence Si into sequences Li, Ei, Gi
3. each sequence Li is connected L where indexing into the shared array is done through the sum of |Li|
4. each processor write Li into L and then repeast the same steps for Ei and Gi 
```
The analysis of such algorithm could be:
- $t(n) = O(\log(N)+n/N) \simeq O(n/N)$ for small N
- $c(n) = O(n)$
- *Optimal*
### Finding k-th smallest element
Finding the k-th smallest element in an array can be done through an algorithm such as:
```
procedure PARALLEL SELECT(S, k) 
1. if |S| < 4 
   then find imediatly the k-th element 
   else divide S into N subsequences Si of length n/N and every sequence Si assert to a processor Pi 
2. for i=1 to N 
   do in parallel M[i] = SEQ.SELECT(Si, |Si|/2) 
   end for 
3. m = PARALL.SELECT(M, |M|/2) with the lowest number of processors 
4. PALALLEL SPLITTING(S, m) 
	L = {𝑠𝑖 𝜖 𝑆: 𝑠𝑖 < 𝑚} 
	E = {𝑠𝑖 𝜖 𝑆: 𝑠𝑖 = 𝑚} 
	G = {𝑠𝑖 𝜖 𝑆: 𝑠𝑖 > 𝑚} 
5. if |L| > k 
   then PAR.SELECT(L,k) 
   else if |L| + |E| > k then return m else PAR.SELECT(G, k-|L|-|E|) 
```
The analysis of such algorithm could be:
- $t(n) = O(n)$ 