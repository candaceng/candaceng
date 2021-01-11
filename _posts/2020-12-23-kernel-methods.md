---
title: "Kernel Methods"
date: 2020-12-23
tags: [Machine Learning]
excerpt: "A trick to solve non linear problems with a linear classifier"
---

One way to approach a classification problem is to find a boundary that separates each class. Linear classifiers are easy to compute but do not perform well in non linear problems where the decision boundary may be quadratic or circular. The general idea of the kernel method is to represent the data in a higher dimension so that the classes are linearly separable. 

### How do kernel methods work?
The kernel trick involves a kernel function *k* that efficiently computes inner products of two variables *x* and *y* in a high dimensional space without actually visiting this space. When the original *n* dimensional feature space of the data is transformed into a higher *m* dimensional space, the dot product of *x* and *y* becomes f(x)<sup>T</sup>f(y) where f is an unknown function that performs the transformation. The kernel function computes this value in terms of the inner product of *x* and *y*, and is not dependent on the transformation function *f*.

### Support Vector Machines (SVM's)
Of all the models that make use of the kernel method, SVM is the most popular. Two inputs *x* and *y* that have a circular boundary in two dimensions can be linearly separated by a plane in three dimensions. The data points closest to the linear classifier are called *support vectors* and the goal of the model is to find the separator that maximizes its distance from these points. 

### Some points to keep in mind
Models are prone to overfitting when using kernel methods and regularization techniques should be used to allow the model to generalize well. Though kernel functions are computed relatively efficiently, the computational cost can still be too high if the number of training examples or dimension space is large. There may also be more hyperparameters to tune depending on the kernel function that is used. 




