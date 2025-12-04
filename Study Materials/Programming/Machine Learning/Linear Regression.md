---
tags:
  - IZU
  - SUI
  - to_be_finished
aliases:
  - linear regression
  - LR
  - ML-LR
---
The task of **Linear Regression** is to learn parameters of a linear function from a set of training data represented by pairs of input values **x** and desired output **y**. For example we can try to learn parameters $w_{0}$ and $w_{1}$ of a linear function from training examples, which are pairs of $x_{n}$ input and desired output $t_{n}$, such that we can then estimate desired outputs for new "unseen values":
$$y = f(x) = w_{1}x+w_{0}$$
For this it can be assumed that there is a linear trend in the training data, which is altered by some random (Gaussian) noise.
## Calculating Parameters
For simplicity in calculations we can rewrite $y=w_{1}x+w_{0}=\hat{x}^Tw$ where $w=\begin{pmatrix} w_{0} \\ w_{1} \end{pmatrix}$ and $\hat{x}=\begin{pmatrix} 1 \\ x \end{pmatrix}$.
1. We search for parameter $w_{0}$ and $w_{1}$ that minimizes the *sum of squares error* objective function:
$$E(w_{0},w_{1})=\frac{1}{2}\sum^N_{n=1}(t_{n}-y_{n})^2 = \sum^N_{n=1}(t_{n}-\hat{x}^T_{n}w)^2$$
2. 