---
title: "Generative Models"
date: 2020-10-23
tags: [Machine Learning]
excerpt: "An introduction to generative machine learning models"
---

One application of unsupervised machine learning is to generate a new dataset based on one that is already known. This is achieved by analyzing the training data and coming up with new examples that has the same probability distribution. An introduction to the most common distributions used in machine learning can be found [here]({% link _posts/2020-09-23-distributions.md %})

Generative models differ from discriminative models in that we are not trying to model the probability of an event given a set of observations, but rather produce never seen before data given a set of training examples. These models are able to generate images, music by genre, a body of text, etc.

Some popular generative models include:
1. Variational Autoencoders
2. Generative Adversarial Networks
3. Energy Based Models

### Variational Autoencoders
In general, autoencoders take in a set of training examples and encode them in a way that the model can easily interpret. For example, a string of text can be encoded into a vector of numbers to allow mathematical operations to be performed. These representations are learned and patterns are detected to try and reproduce the input, before being decoded back into a form that is understandable to humans. Variational autoencoders differ from regularized autoencoders such as sparse or denoising autoencoders in that they generate new examples of the input rather than optimizing parameters of a probability distribution. 

### Generative Adversarial Networks
The motivation behind generative adversarial networks (GAN's for short) is to have two networks that oppose one another; one model's gain is the other model's loss. In applications such as image or music generation, there is a generator that simulates an input and a discriminator that tries to differentiate between the real input and the one that was generated. The generator is always trying to create more realistic examples while the discriminator is always trying to identify the real training example. GAN's are also commonly used in two player games such as Chess and Go, or even in video games involving strategy such as StarCraft. 

### Energy Based Models
The aim with energy based models (EBM's) is to minimize the energy function that certain configurations of variables are measured on during inference. This is analogous to field of physics, as the second low of thermodynamics which states that energy decreases to a minimum at equilibrium. The energy function differs from the minimization of the loss function, which is continually applied during the learning process as opposed to being applied at prediction time. Common applications of EBM's include face recognition, sequence labelling, and the restoring of images. 