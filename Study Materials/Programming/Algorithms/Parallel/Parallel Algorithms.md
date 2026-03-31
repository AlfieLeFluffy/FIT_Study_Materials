---
tags:
  - PRL
aliases:
  - parallel algorithms
sources:
  - "[[PRL_02_Search_and_Sort.pdf]]"
---
Parallel algorithms are ones that run on multiple [[Microprocessor|processors]] at the same time while communicating.
## Analysis
There are several parameters that can analysed, such as:
- **Number of processors** 
	- (*p*) of processors required to solve the task with input size *n*
- **Time** required to solve a task in number of steps
- **Cost** of parallel solution
	- $c(n)=p(n)\times t(n)$
	- An algorithm has an optimal cost: $c_{opt}(n)=t_{seq}(n)$ time for solution in sequential solution
- **Speed-up** x **Effectivity**
	- Speed-up is: $t_{seq}(n) / t(n)$
	- Effectivity is: $t_{seq}(n) / c(n)$, which also takes into account number of processors where anything under 1 is sub-optimal, anything around 0 is optimal