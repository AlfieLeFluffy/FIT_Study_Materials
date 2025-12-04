---
tags:
  - IZU
  - SUI
  - to_be_finished
aliases:
  - supervised learning
  - SL
  - ML-SL
---
# Supervised Learning
Also known as **Learning with a Teacher** is [[Machine Learning|machine learning]] based upon the principle that with **each step** of the learning process *the required response is known*, so the system is immediately informed of the *current evaluation of the last action*. 
This learning is done on a set of training examples **T**, where each example is represented by a *set of input variables* (input vector) and a *set of correct or required output values* (output vector).
## Tasks
Common tasks supervised learning is used for are:
- **Classification** is that given training examples (coloured dots), learn to assign class (colour) to new "unseen" observations.
	- Recognize persons identity from an image.
	- Classify objects from parameters.
	- Classify facial expressions from a video.
- **Regression** is that given training examples, learn to predict likely values for new "unseen" observations.
	- Predict stock prices using previous company observations.
	- Predict weather from past meteorological measurements.
- **Basic Pattern Recognition**
	- Recognize words in speech recordings.
	- Detect and classify all known objects in a video.
	- Estimate poses of every person in a video.
- **Other**
	- Translate text from one language into another.
	- Automatically describe image.
	- Generate realistic image from text description.
## Classification
For classification in supervised learning [[Classifier|classifiers]] are commonly used.
![[Classifier]]
## Algorithms
Supervised methods work with vectors, that have symbolic values (numeric values are also symbolic) and are based on the assumption that each hypothesis, that satisfies a big enough set of training data, will be satisfying even to unknown examples.
![[Decision Tree Building]]

![[Version Space Search]]

## Pattern Recognition and Classification
For recognition of pattern there exist several algorithms, that work with one of the next description of the objects:
- **Symptomatic Description** (vectors of numeric symptoms) use static information about image symptoms contained in the training data set. This can be through of as a list of information containing things like number of segments, horizontal segments, vertical segments, diagonal segments, etc.
- **Structural**/**Syntactic** (structural element or primitives) use relations between image symptoms of the recognized objects. This can be through of as a graph of nodes each corresponding to a primitive such as horizontal and vertical lines.
A necessary assumption is that successful recognition is a selection of relevant symptoms or primitiv.
### Symptom Recognition
A sign recognition works with:
- **n-dimensional number vectors** of signs that describe the recognized object
- **Set of classes** into which the objects can be classed into.
- **Training set** comprised of doubles of n-dimensional number vectors and a class into which the object belongs.
The goal is the classifications of any vector of symptoms into one of the classes. These methods are based on the assumption that images of objects or phenomena classed into the same class create in n-dimensional space **groups**. These groups can be from each other easily distinguished (**separable**) or they can intersect one another (**inseparable**). Systems that learn and then recognize new objects are called **classificatory**.
#### Dichotomie
It is classification into **one of two classes**. In practice **dichotomie** is quite common, generally it is classification into **N** classes, which is based on finding of **curves/areas/k-polynoms** that create images of each class and separate one from the another. This can be ensured by a **discrimination** function (for each class one) that can evaluate an image. An image is then classed into a class that has the highest evaluation. In dichotomie we can use just one function (two of them that we subtract) and the classification is then based on the sign.
#### Etalony
It uses center of gravity of image clusters. An image is classed to which **etalone** it is closest to. This method still uses a discrimination functions.
#### Recognition of Images Represented by an Inseparable Classes
In case of inseparable classes it cannot be determined if an image goes into class **r**, but it can be said that the image goes into a class with probability **P(r|x)**. The goal of the training algorithm is to find such classificators that will class images with the highest probability, in other words they try to minimize loss that is create by classification into an incorrect class. For this a loss [[Matrix]] is used and a loss for a correct classification is 0 and for incorrect it is 1. Based on this the matrix is simplified.
### Structural Recognition
Structural recognition does classification of images using primitives. There exist two basic ways for structural classification:
- Using **Grammar** (Syntactic Recognition)
- Using **Comparision with Patterns** that are saved in a database.
**Syntactic** recognition classes object into R classes based on an **syntactic analysis**.
#### Freeman Chain Code
This code is used to create a structural description of an objects outline. The primitive describing the objects outline are directions to the neighbours. Problem with this is their rotation and starting position, but they can be eliminated:
- **Rotation** can be solved by using relative (differential) code, that instead of neighbour directions uses **ratio/difference in rotation** between each neighbour. 
- **Starting Position** can be solved through rotating the number around until its the biggest number possible.
The final **shape number** is then invariant against transposition, rotation and starting point, but it is still dependent on its size.