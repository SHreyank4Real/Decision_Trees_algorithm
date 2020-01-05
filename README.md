# ID3 Decision Trees Algorithm

This README outlines the details Decision Tree algorithm in machine learning

## Prerequisites

You will need the following things properly installed on your computer.

* [python3.6](https://www.python.org/downloads/)
* numpy
* matplotlib 
* pandas
* dataset 

or you can use google colab notebook
* https://colab.research.google.com

## Explanation
ID3 it's a recursive algorithm that produces as its output a new algorithm that performs classification. Classification is a problem where we're given a thing that has one or more attributes and we're asked to decide what class it belongs to. For instance, the thing could be an email and the classes could be "spam" and "ham".

The way ID3 takes the examples it's given and tries to plan out which questions most reduce its uncertainty about the class. Entropy comes into it here, because entropy is how we quantify how uncertain we are. The entropy of a set of examples is defined as the sum over all classes of (proportion of examples belonging to the class) * log*2(proportion) * -1. This gives you a number between 0 and log2*(class count) which neatly quantifies your uncertainty about what class a randomly chosen member of the examples belongs to. It's at its maximum when every class is equally likely, and shrinks smoothly to 0 as the set becomes more skewed toward a particular class.

For each attribute, ask all the examples what value they have for that attribute. Divide all the examples into new sets so that all the members of each set have the same value for that attribute.
For each attribute, add together the entropies of all the new sets it produced.
The attribute that produced the smallest entropy is the one that most reduced our uncertainty. At this point in the questioning, we should ask what that attribute is.
To figure out what questions we should ask after that one, we do ID3 recursively on the sets of examples we got from asking about the chosen attribute. If any of those sets contain only one class, the classifier can complete here and just return that class.
