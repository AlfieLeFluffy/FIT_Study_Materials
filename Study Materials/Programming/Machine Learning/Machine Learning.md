---
tags:
  - IZU
  - SUI
aliases:
  - ML
  - machine learning
---
# Machine Learning
**Machine learning** is the ability for an inteligent system to change its knowledge in a way to so it can do the same task more effectively and efficiently.
A typical task for machine learning is to take an *input observation*, run this input through a *model/algorithm* and give an output based on it. 
### Machine Learning Task Examples
Examples of such tasks can be:
- Recognize words in a speech recording.
- Recognize person identity from an image of their face.
- Translate Czech text to Korean.
- Classify object from its parameters.
- Predict stock prices using companies' past quarterly revenue results.
### Input Examples
To represent the experiences from which the systems can learn, we commonly use collections **training examples**, which are comprised of inputs and corresponding (expected) outputs. Common examples of inputs are:
- *Speech wave forms*
- *Matrixes* such as pictures
- *Sequence of words*
- *Vectors*
### Evaluation
Common way to evaluate how well the machine learning went is to check using a different set of *evaluation examples* and see how well the system was able to classify/recognize/etc these examples.
## Symbol Convention
- Lowercase letters with sub-letters are exact data, such as x<sub>2</sub>
- Lowercase letters that are bold are vectors, such as **x**
- Uppercase letters that are bold are matrixes, such as **X**
## Training Data
The set of learning data is commonly *divided into two or three subsets*. The first subset is the **training** (~80%), the second is **testing** (~20%) and the last one can be used to **tweak** the final parameters, which is not necessary but can be helpful in certain moments.
## Goals of Machine Learning
The main goal summarized is to take a given *set of training examples* and learn how to map *new "unseen" examples* onto desire output. Examples of this could be:
- Given a data set of hundreds of hours of transcribed speech audio recordings learn to automatically transcribe new speech recordings.
- Given a data set of millions of images of human faces labelled by person identity learn to recognize person identity in a new image.
## Types of Machine Learning
There are four main types of machine learning:
- [[Supervised Learning]]
	- Training examples are pairs of inputs and desired outputs.
	- Typical tasks are classification, more general pattern recognition, regression, etc.
- [[Unsupervised Learning]]
	- Training examples is only unannotated input data.
	- Typical tasks are clustering, anomaly detection, density estimation, etc.
- [[Semi-supervised Learning]]
	- Some of the training data is annotated (input/output pairs), but there is also unannotated data available for training.
- [[Reinforcement Learning]]
	- Feedback driven learning in which system learns incrementally through incorporating feedback into its decisions.
	- Typical tasks are learning to drive autonomous vehicles, learning to play a computer or board game, etc.
---
### Sources:
- [[SUI_01_Classification_and_Recognition.pdf]]