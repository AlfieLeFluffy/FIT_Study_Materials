**Learning without a Teacher** is based upon searching for similarities between examples of the training data and classification of example with similar characteristics into groups. An artificial system does not receive any information about the correct or incorrect classification and the only information that it can have is the number of groups, into which the training data can class into.
An example of a training set is pretty much always a set of number vectors that signify objects or a phenomenon. Methods are then based on the assumption that these vectors or points are classed into **n-dimensional groups** (image space). These **groups** can be imagined as very chaotic **n-dimensional shapes**. 
### K-means Clustering
This algorithm classes examples from the training data into predefined **k groups**. Algorithm classes vectors into groups based on to which **center of gravity it is the closest**. The input into this algorithm is the number of groups **k** (must be bigger then the number of vectors).
#### Steps
1. Randomly select **k** number of vectors (from the training data). These vectors are assumed to be centres of gravity for the groups.
2. Class all vectors of the training data into groups based on their distance from the centres (Euclidian distance, Hamming distance).
3. **Recalculate the centres** of the groups.
4. If the position of neither center changed then the algorithm ends. Otherwise repeat from step 2.