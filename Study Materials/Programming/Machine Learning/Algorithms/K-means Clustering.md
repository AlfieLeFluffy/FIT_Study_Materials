---
tags:
  - IZU
  - SUI
  - to_be_finished
aliases:
  - k-means clustering
---
## K-means Clustering
K-means Clustering is an example of [[Unsupervised Learning|unsupervised learning]] algorithm that classes examples from the training data into predefined **k groups**. Algorithm classes vectors into groups based on to which **center of gravity it is the closest**. The input into this algorithm is the number of groups **k** (must be bigger then the number of vectors).
#### Steps
1. Randomly select **k** number of vectors (from the training data). These vectors are assumed to be centres of gravity for the groups.
2. Class all vectors of the training data into groups based on their distance from the centres (Euclidian distance, Hamming distance).
3. **Recalculate the centres** of the groups.
4. If the position of neither center changed then the algorithm ends. Otherwise repeat from step 2.