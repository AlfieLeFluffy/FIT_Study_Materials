---
tags:
  - IZU
  - SUI
aliases:
  - classifier
  - machine learning classifier
  - ML Classifier
  - ML classifier
---
# Classifier
A [[Machine Learning|machine learning]] object that based on a set of training objects and their features (parameters) classifies new objects into desired classes.
## Discriminative Feature
A discriminative feature is an object's feature by which it can be easily classed into a correct class. 
For example a when trying to class tenis balls from oranges, their size and roundness is not a great discriminative feature as these objects have a rather big overlap in these features, but colour would be a good discriminative feature as tennis balls are usually green and oranges are usually orange, thus the overlap between the objects in this parameter would be low.
### Finding Discriminative Features
There is no general way of selecting discriminative features, but the main idea is to select the features in which the objects (classes) have the least overlap in. A good way of doing this is to plot the features onto histograms and or create Gaussian (normal) distributions for the features and compare them.
### Multivariable Features
Also known as **Input Patterns**, are a combinations of features that in combination create a better distinction (less overlap) together then apart. These features can be plotted onto point (dot) graphs for better visual representation.
To return to previous example of oranges and tennis balls, we could combine the object's colour with the object's weight to create a multivariable feature that can be better then just colour alone, as tennis balls are usually lighter then oranges.
## Classification
The goal of classification is to find a good **decision boundary**, that separates examples of one class from another (others). New observations then can be checked against these decisions boundaries to find out into which class they should belong.
### Generalization
A common issue with classifiers is generalization. This happens when the selected method of classification is too specific to the training data and creates issues when classing new observations. For examples this could be creating a decision boundary complex and that encompasses all training data of one class to a point, where new data can be commonly misclassified because of outlier training data pushing the boundary where it should not.
## Classifier Types
There are many types of classifiers that depend upon the chosen way of representing the decision boundary.
### Linear Classifier
A classifier of which decision boundary is given by a linear function $f(y) = ax + b$ that splits the training data into two sections and new observations are placed on either side of it.
### Quadratic Classifier
A classifier similar to the *Linear Classifier*, but instead of a linear function that spit the training data, it uses a quadratic function that can can better divide the examples into correct classes.
### K-nearest Neighbours Classifier
A classifier that should not be confused with [[K-means Clustering]] and is a *nonparametric classifier*, meaning the classifier has no parameters to train or estimate. It needs to remember all training examples and to assign a new observation a class it finds K nearest examples (neighbours) in the training data and chooses the more represented class.
Choosing the right K value can drastically improve the classifier performance as a small K can lead to solutions that can be too specific and a high K can lead to solutions that can be too general (over trained).
An expansion of this classifier is to use a soft decision space, where the final outcome is not represented as one specific class the observation is classed into, but as a ration (probability) of the classifier falling into each class.
### Generative Classifier
Generative classifiers use models of the training data as [[Probability Distributions and Transformation|probability distributions]] to classify new observations. The next section goes into depth on this topic.
## Generative Model Classifier
A generative classification models observed data into distributions and then using probability of new observations being in said distributions to classify them.
### Probabilities Used in Generative Classifier
Some basic probability rules that are useful within these classifiers are [[Basic Probability#Bayes' Formula|Baye's rule]], [[Random Vector#Sum Rule|Sum rule]] and [[Random Vector#Product Rule|Product rule]].
Other useful probabilities:
- *P(class, observation)* is joint probability.
	- Probability of an observation being in class.
	- In generative classifier this is used to normalize the counts by the total count gives *Maximum likelihood (ML) estimation*.
- *P(class)* is the marginal probability.
	- Prior probability of a class. 
	- This is usually given by a Gaussian (Normal) distribution created by maximum likelihood estimation of the training data.
- *P(class| observation)* is conditional probability.
	- Posterior probability of a class given an observation.
	- Maximum a-posteriori classifier selects the most likely class.
### Generative Model For Continuous Observations
The maximum a-posteriori classification rule says: "select the more likely class"
$$P(\text{class|observation}) = \frac{p(\text{observation|class})P(\text{class})}{p(\text{observation})}$$
$$p(\text{observation}) = \sum_{class} p(\text{observation|class})P(\text{class})$$
### Multi-Dimensional Gaussian Classifier
- Class priors can be estimated with maximum estimation as the proportions of the example counts:
$$P(c) = \frac{N_{c}}{\sum_{K}N_{k}};\text{k is all class}$$
- Parameters of the distribution can be estimated as:
$$\mu_{c}=\frac{1}{N_{c}}\sum_{n=1}^{N_{c}}x_{cn}\ \ ; \ \ \Sigma_{c}=\frac{1}{N_{c}}\sum_{n=1}^{N_{c}}(x_{cn}-\mu_{c})(x_{cn}-\mu_{c})^2$$
- Probability density function for each class is assumed to be 2D Gaussian distribution:
$$p(x|c) = N(x; \mu_{c},\Sigma_{c})$$
- Class posterior probability for new observations is obtained from the prior and the class pdf-s using Bayes rule:
$$P(c|x)=\frac{p(x|c)P(c)}{\sum_{k}p(x|k)P(k)}$$
---
### Sources
- [[SUI_01_Classification_and_Recognition.pdf]]