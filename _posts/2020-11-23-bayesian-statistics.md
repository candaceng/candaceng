---
title: "Bayesian Statistics"
date: 2020-11-23
tags: [Data Science, Machine Learning]
excerpt: "Understanding the Bayesian approach to statistical inference"
---

There are two schools of statistical inference - the Bayesian and the frequentist approaches. The frequentist approach simply estimates the probabilty of the observed data *D* given a hypothesis *H*. In contrast, the Bayesian approach uses the probabilities of both the hypothesis and the data. Specifically, it is dependent on the *prior* distribution, the *posterior* distribution, and the total probability of the data *P(D)*. There are pros and cons to this approach. 

### Pros
Using Bayesian inference makes logical sense in many situations because having prior information about a certain event makes the deduction process easier. For example, if I have misplaced my phone, I can create a probability distribution of where my phone can be (frequentist approach). Alternatively, I can use prior information of where I have misplaced myu phone in the past to deduce its location quicker (Bayesian approach). 

### Cons
The probability distribution of the prior is subjective, and different priors will yield varying results. There is no defined way of choosing a prior, but this issue can be addressed by stating the underlying assumptions made to reach the choice of distribution. Bayesian inference is also computationally expensive as there are many more parameters needed to be integrated over when compared to the frequentist approach. 
<br>
<br>
<br>
Given the power of modern day machines, many researchers have started to explore the use of Bayesian statistics in large scale applications. For small datasets, this approach may not perform as well, given that it is dependent on the posterior distribution which is continually updated as data is being read in. More training data tends to correlate with better generalization and higher accuracy. 

