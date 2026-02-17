---
tags:
  - IZU
  - SUI
  - to_be_finished
aliases:
  - unsupervised learning
  - UL
  - ML-UL
---
# Unsupervised Learning
Also known as **Learning without a Teacher** is [[Machine Learning|machine learning]] based upon searching for similarities between examples of the training data and classification of example with similar characteristics into groups. 
The system does not receive any information about the correct or incorrect classification and the only information that it can have is the number of groups, into which the training data can class into.
A common example of training data is a set of vectors that represent objects or a phenomenon. Methods are then based on the assumption that these vectors or points are classed into **n-dimensional groups** ([[Image]] space). These **groups** can be imagined as very chaotic **n-dimensional shapes**. 
## Tasks
Common tasks unsupervised learning is used for are:
- **Clustering** is finding clusters of "similar examples" in the input data.
	- In collection of documents find similar documents.
	- In a recording of a conversation, find and cluster segments spoken by the same person.
- **Anomaly Detection** is detecting unusual inputs in other words it is trying to find outliers.
	- Refuse outliers before further processing.
	- Point out outliers as particularly interesting.
- **Density Estimation** learns the probability density function from data. This can be from example learning a simple Gaussian (Normal) Distribution from data, but there are more complex options such as neural networks that can learn complex distribution and generate new samples from it.
## Algorithms
![[K-means Clustering]]