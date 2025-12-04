---
tags:
  - MSP
  - to_be_finished
aliases:
  - indicator random variable
  - indicator random variables
  - IRV
---
Given a sample space **S** and an event **A** in **S**:
- Indicator random variable for **A** is defined as $I\{A\} = 1$ if **A** occurs, 0 otherwise.
- Let $X_{A} = I\{A\}$, it holds that $E[X_{A}]=Pr\{A\}$ is the probability of A occurring.
### Key Idea
The key idea is the express the expectation of a random variable ($X$) as the expectation of the sum of components that are easier to count (the indicator variables $X_{i}$)
### Examples
#### Coin Toss
What is the expected number of heads (**H**) in **n** coin flips?
- $X_{i}=I\{\text{i-th coin flip results in event H}\}$ where $Pr\{X_{i}\} = E[X_{i}] = \frac{1}{2}$
- $X=\sum_{i=1}^{n}X_{i}$
- $E[X] = E\left[ \sum_{i=1}^n X_{i} \right]$ due to linearity we obtain $E[X] = \sum_{i=1}^n E[X_{i}] = \frac{n}{2}$
#### Hiring Problem
Given the algorithm and assuming a random order of candidates:
```
Hire-Assistant(n):
	best = 0
	for i from 1 to n:
		interview candidate i
		if candidate i is better then best:
			hire cindidate i -> paying cost c_h
			best = i
```
We can define the random variables $X_{i} = I\{\text{i-th candidate is hired}\}$ and:
- $X = \sum_{i=1}^n X_{i}$ is the total number of hired candidates or the cost.
- $E[X]$ is the expected cost of the algorithm.
- $E[X_{i}]$ is the probability of the i-th candidate is hired.
- Candidate $i$ is hired if it is better then candidates $1,2,\dots,i-1$
- $E[X_{i}]=\frac{1}{i}$
- $E[X] = E\left[ \sum_{i=1}^n X_{i}\right]= \sum_{i=1}^n E[X_{i}] = \sum_{i=1}^n \frac{1}{i} = \ln(n)+O(1)$
