---
title: "Probability Distributions"
date: 2020-09-23
tags: [Machine Learning, Statistics]
excerpt: "An introduction to common probability distributions"
---

In machine learning, we often want to estimate the parameters of a function that would yield the most likely event/outcome. Probability distributions are such functions, and there are many different distributions used to model certain situations. 

Given a random variable *Y*, the likelihood function is given by *P(Y = y; x)* where *P* is the probability distribution and *x* represents any number of parameters. Random variables can be discrete or continous - but in either case, the area under the distribution should equal to 1. 

Here, we'll go over the following probability distributions that are commonly used in machine learning:
1. Gaussian 
2. Uniform
3. Binomial
4. Poisson
5. Exponential

### The Gaussian distribution
Known as the bell curve, this continuous distribution is parameterized by the mean and variance of the observations of a random variable. The distribution is symmetrical and centered about the mean, with 95% of probabilities within two standard deviations of the center. This is often useful for constructing confidence intervals in the estimation of model parameters, and the 95% confidence interval is most commonly used. 

### The Uniform distribution
This is an easy one - all the values of a given set have the same probability. For a wider range of values, the distribution appears shorter to keep the area under the function equal to 1. For example, a set of numbers with a range of 5 values would imply that each value has a probability of 0.2. Similarly, a set of numbers with a range of 10 values would imply that each value has a probability of 0.1.  

### The Binomial distribution
Here, events have two possible outcomes - one has a probability of *p* and the other has a probability of 1 - *p*. A single trial of this event would indicate that this is a *Bernoulli random variable*. The sum over multiple trials of an event with two possible outcomes is what makes up a binomial distribution. It is a discrete function that indicates the probability of *x* successes in a series of *n* trials. 

### The Poisson distribution
This discrete distribution is used to models the average number of occurences of an event in a given period of time. The Poisson process is *stochastic*; an event can occur over two consecutive time periods but could also occur many time periods apart. However the expected number of occurences does not change, and this is the parameter that defines a Poisson distribution. 

### The Exponential distribution
The expected amount of time that passes between two occurences of the same event is typically modelled by the exponential distribution. It is a continuous function and can be parameterized by a rate parameter (indicates how quickly the function decays) or a scale parameter (the inverse of the rate parameter). 
