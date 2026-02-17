---
tags:
  - TIN
aliases:
  - computable function
  - Computable Functions
  - computable functions
sources:
  - "[[TIN_04_Turing_Machine.pdf]]"
---
## Computable Functions
A computable functions are restricted through [[Turing Machine Coding|TM coding]] to functions of a shape:
$$f:\mathbb{N}^m\to \mathbb{N}^n$$
where $\mathbb{N} = \{ 0,1,2,\dots \}, \ \ m,n\in \mathbb{N}$. The convention is that the n-tuple $(x_{1},x_{2},x_{3},\dots)\in \mathbb{N}^m$ will be described as $\overline{x}$.
### Classification
There are two classes of computable functions:
- **Total Function** is defined for each $\overline{x}\in \mathbb{N}^m$.
- **Strictly Partial Function** is defined as $\exists \overline{x}\in \mathbb{N}^m:f(\overline{x})=1$.
## Elementary Function
Hierarchy of computable functions is based on **elementary functions**, that are the **building blocks** of higher functions.
### Examples
Amongst the types of elementary functions we have:
- **Null Function** maps an empty n-tuple $\epsilon()=0$ onto 0. 
- **Successor Function** maps as $\sigma:\mathbb{N}\to \mathbb{N}$ or $\sigma(x)= x+1$.
- **Projection Function** maps as $\pi_{k}^n:\mathbb{N}^n \to \mathbb{N}$. Selection from a n-tuple the k-th element, such as $\pi_{2}^3(7,6,4)=6$ and $\pi_{1}^2(5,17)=5$. A special case is $\pi_{0}^n:\mathbb{N}^n\to \mathbb{N}^0$, such as $\pi_{0}^3(1,2,3)=()$.
## Complex Function
With the elementary functions, a more complex functions can be created by combining the elementary functions together.
### Examples
Some examples of complex functions are:
- **Combination** is a combination of two functions $f: \mathbb{N}^k\to \mathbb{N}^n$ that works as $f\times g:\mathbb{N}^k\to \mathbb{N}^{m+n}$ where $f\times g(\overline{x})=(f(\overline{x}),g(\overline{x}),\overline{x}\in \mathbb{N}^k)$.
- **Composition** is a composition of two functions $f:\mathbb{N}^k\to \mathbb{N}^m$ and $g:\mathbb{N}^m\to \mathbb{N}^n$ that works as $g \circ f:\mathbb{N}^k\to \mathbb{N}^n$ where $g \circ f(\overline{x}) = g(f(\overline{x})),\overline{x}\in \mathbb{N}^k$.
- **Primitive Recursion** is a technique that allows the creation of function $f:\mathbb{N}^{k+1}\to \mathbb{N}^m$ based on two functions $g:\mathbb{N}^k\to \mathbb{N}^m$ and $h:\mathbb{N}^{k+m+1}\to \mathbb{N}^m$ that works as $f(\overline{x},0)=g(\overline{x})$ and $f(\overline{x},y+1)=h(\overline{x},y,f(\overline{x},y)),\overline{x}\in \mathbb{N}^k$.
	- Function $mult$ can be defined as $mult(x,0)=0$ and $mult(x,y+1)=x+mult(x,y)$.
## Primitive Recursion Function
A class of primitive recursion functions is a class of total functions that can be created from elementary functions by finite application of:
- combination
- composition 
- primitive recursion. 
A characteristic of these functions is that they can be written as a computer program that contains only **finite for** cycles and **no while** cycles and **no jumps**. 
There exist functions that are enumerable and are not primitively recursive functions and are strictly partial functions such as $div$ but also total functions. There also exist total functions from $\mathbb{N}$ to $\mathbb{N}$ that are not primitively recursive.
## Partially Recursive Function
A class of partially recursive functions are functions that can be made from elementary functions by applying:
- combination
- composition
- primitive recursion
- minimalization
## Turing Computable Function
A [[Turing Machine|Turing machine]] $M$ can compute partial function $f:\Sigma^{*m}\to\Sigma^{*n}_{1},\Sigma_{1} \subseteq \Gamma,\Delta \not\in\Sigma_{1}$ if for every $(w_{1},w_{2}w,3,\dots)\in\Sigma^{*m}$ and corresponding initial configuration $\underline{\Delta}w_{1}\Delta w_{2}\Delta w_{3}\Delta\dots w_{m}\Delta^w$ can the machine $M$:
- In case that $f(w_{1},\dots w_{m})$ is defined then $M$ stops and the tape contains $\underline{\Delta}v_{1}\Delta v_{2}\Delta v_{3}\Delta\dots v_{m}\Delta^w$ where $(v_{1},v_{2},v_{3}\dots v_{n}) = f(w_{1},w_{2},w_{3},\dots w_{m})$.
- In case that $f(w_{1},\dots w_{m})$ is not defined then $M$ cycles or stops abnormally.
Partial functions that can be computed by some [[Turing Machine|Turing machine]] are **Turing computable** functions. Each partially recursive function is **Turing computable**. Each computing process done be a [[Turing Machine|Turing machine]] is a process of computing some partially recursive function.
## Hierarchy of Functions
Each class of functions is within one hierarchy that goes from the lowest to the highest, with each tier being a subset of the next one:
1. Elementary Functions
2. Primitive Recursive Functions
3. $\mu$-recursive Functions
4. Partially Recursive Functions - [[Turing Machine|Turing machine]] computable functions
5. All Functions
The class of totally computable functions is $\mu$**-recursive functions**. An example of a function that is **not Turing computable** is:
$$f(w) = \begin{cases} 
|w| & w\in L \\
0 & w\not\in L
\end{cases}$$
where $L$ is any [[Formal Language|language]].