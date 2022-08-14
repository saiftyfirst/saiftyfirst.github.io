---
layout: post
title:  "Mean-field Approximation"
date:   2022-07-26 20:29:32 +0200
categories: jekyll update
---
## Introduction
The mean-field approximation is a widely used technique used to study the approximate dynamics of a population of identical elements. In Computational Neuroscience, the technique is often employed to study the overall dynamics of a large population of neurons. 

### Firing rates of a population of neurons 
**Input current to a single neuron**
When studying a population of neurons, we are often interested in the firing rate of an arbitrary neuron in the population, where firing rate refers to the number of times the neuron is activated over a unit interval of time. 

Consider a population of N fully-connected neuorons, i.e. each neurons is connected to every other neuron except itself (no recurrence). At any particular moment in time, a neuron, i, recieves an external input current, $$I_{ext}$$, and a synaptic current, $$I_{syn}$$. The external current is injected from external sources such as  sensory pathways, for example. The synaptic current, on the other hand, is an aggregation of the currents that the neuron receives by virtue of its connectedness with the rest of the neurons in the population (when a neighboring neuron, j, fires at time t, it contributes to $$I_{syn}(t)$$ of neuron i).

\begin{equation}
I_{i}(t) = I_{ext}(t) + I_{syn}(t) 
\tag{1}\end{equation}

In the following sections, we lay out the idea of measuring the average firing rate of a population of neurons, the compuatational complexity that we face and how the mean-field approximation idea can help us obtain estimates.


**The transfer function** [1]
The relationship that describes how the firing rate, $$f_i$$, of neuron i dependson the overall input current into the neuron is referred to as the transfer function and can be formulated as follows:
\begin{equation}
f_{i}(t) = S ( I_{i}(t))
\tag{2}\end{equation}

From the trasfer function, if we wish to obtain the mean firing rate, we can attempt to calculate the expected value of the right-hand side of equation 2:
\begin{equation}
\langle f_{i}(t) \rangle = \langle S ( I_{i}(t)) \rangle
\tag{3}\end{equation}

**The motivation for mean-field analysis** [1]
The motivation for mean field analysis comes from problem faced when we wish to evalutate (3). The component $$I_{syn}(t)$$ in $$I_{ext}(t)$$ depends on the state of each of the neighboring neurons of i at each point in time. This mean, when we wish to evaluate (3), we must account for all the states of each neighbor including their probalities of being in a particular state and the effect of being in that state that it has on neuron i. Concretely, let $$x(t)$$ represent the vector of states of all neigbors of neuron i. Then we can rewrite (2) and (3) as follows:
\begin{equation}
f_{i}(t) = S ( I_{i}(x(t)))
\tag{4}\end{equation}
\begin{equation}
\langle f_{i}(t) \rangle = \langle S ( I_{i}(x(t))) \rangle = \sum_{x}S(I_{i}(x(t)p(x(t)))
\tag{5}\end{equation}
where $$p(x(t))$$ is the probaility that the neigbors are in state $$x$$.

The above expecatation presents a complex challenge. We would like to estimate the mean firing rate instead of trying to get an exact solution from the above equations. To that end, we make the following mean-field assumption:
\begin{equation}
S ( I_{i}(x(t))) =  S ( \langle I_{i}(x(t)) \rangle)
\tag{6}\end{equation}

In essence, we admit that evalution of the actual mean firing rate is something we wish to avoid. Instead, we evaluate the mean of the input current into the neuron and hope that evaluating the transfer function with the mean input current gives us a reasonable estimate for the firing rate (Since the mean current is not a random variable, the traingle brackets can be removed from $$\langle S(.) \rangle$$).


In the following sections, let us bring the idea home with neuron models that have been widely used in research.


### Example 1: Binary Neurons [1]
A binaty neuron is characterized by consisting of two states, spiking or not, $$x_i \in \{0,1\} $$. When such neuron models are used, the current $$I_{i}$$ into neuron i can be represented as follows:
\begin{equation}
I_{i} = \sum_{J_{j \neq i}}^{N}J_{ij}x_j + I_{i,ext}
\tag{7}\end{equation}
 


### Example 2: LIF Neurons

### Example 3: Mean-field Approximation in a Model of Visuospatial Working Memory

### The validity of mean-field approxmiation

### References

