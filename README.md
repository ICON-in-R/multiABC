# Approximate Bayesian Computation (ABC) for multiple data sets

One sequential approach is to use the ABC posterior after analysing the $i$ th data set as a prior for analysing the $(i+1)$ th data set.

This is an idea take from

> Fearnhead, P. and Prangle, D. (2012) ‘Constructing summary statistics for approximate Bayesian computation: Semi-automatic approximate Bayesian computation’, Journal of the Royal Statistical Society. Series B: Statistical Methodology, 74(3), pp. 419–474. doi: 10.1111/j.1467-9868.2011.01010.x.

## Description

Calculate a set of approximate likelihoods, one for each data set.

$$
p(\theta \mid s_1) = \int \pi(y \mid \theta) K[(S(y) - s_1)/h] \mbox{d}y
$$

$$
p(\theta \mid s_2) = \int \pi(y \mid \theta) K[(S(y) - s_2)/h] \mbox{d}y
$$

$$
\vdots
$$

Then sequentially update each posterior

$$
\pi_{ABC}(\theta \mid s_1) \propto \pi(\theta) p(\theta \mid s_1)
$$

$$
\pi_{ABC}(\theta \mid s_1, s_2) \propto \pi_{ABC}(\theta \mid s_1) p(\theta \mid s_2)
$$

$$
\vdots
$$
