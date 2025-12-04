---
tags:
  - MSP
  - to_be_finished
aliases:
  - randomised algorithms
---
A way to combat/handle adversarial inputs, which are inputs that are not put into a random order, and achieve the expected algorithm complexity for all inputs is **randomisation**.
## Randomisation Types
Commonly, there are two approaches/types to **randomisation**:
1. Randomise the **ordering** of inputs. This can combat the issue of random order in [[IRV Hiring Problem Example]].
2. Randomise **choices** made within the algorithm. Know example of this is [[Quick Sort]].
## Gambling Classification
Through randomisation we can gamble with:
1. **Resources** such as run-time
2. **Correctness** of the outcome
## Algorithm Classification
There are two main types of randomised algorithms:
### Las Vegas Algorithm
![[Las Vegas Algorithm]]
### Monte Carlo Algorithms
![[Monte Carlo Algorithm]]
## Algorithm Analisys
One way to analyse the correctness and complexity of randomised algorithms is through [[Indicator Random Variable|indicator random variable]].
![[Indicator Random Variable]]
## Famous Randomised Algorithms
The are algorithms for hard problems such as:
- Miller-Rabin primality test ([[Monte Carlo Algorithm|MCA]])
	- Advanced algebra and randomisation
	- Existing and practically very useful implementations
- Polynomial identity testing
	- Decide if two given polynomial functions are identical
- Several important [[Graph|graph]] algorithms
	- Perfect matching bipartite graphs, graph isomorphism, etc.
## Disadvantages
Randomisation algorithms are not a silver bullet to every issue, such as SAT.