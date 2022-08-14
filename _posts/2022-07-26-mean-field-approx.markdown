---
layout: post
title:  "Mean-field Approximation"
date:   2022-07-26 20:29:32 +0200
categories: jekyll update
---
## Introduction
Mean-field approximation is technique that can be used to study the approximate dynamics of a population of identical elements. In Computational Neuroscience, the technique is often employed to study the overall dynamics of a large population of neurons. 

### Firing rates of a population of neurons 
**Input current to a single neuron**
In its most widespread application, mean-field approximation can be used to study the firing rates of a population of neurons. Consider a population of N neuorons that are fully connected (each neurons is connected to every other neuron exceot itself - no recurrence). At a particular point in time, neuron i recieves an external input current, $$I_{ext}$$, and a synaptic current, $$I_{syn}$$, which is the aggregated current it receives from the synaptic connections it forms with its neighboring neuorns.
\begin{equation}
I_{i}(t) = I_{ext}(t) + I_{syn}(t) 
\end{equation}

**The transfer function** [1]
Since we are interested in the firing rates of the neurons, the important metric we wish to analyse is how the input current, $$I_i$$ into neuron i affects its firing rate, $$f_i$$. The relationship between the two is given by what is called the transfer (gain/response) function.
\begin{equation}
f_{i}(t) = S ( I_{i}(t))
\end{equation}

The mean firing rate can thus be obtained by finding the expected value of the firing rate expression above.
\begin{equation}
\langle f_{i}(t) \rangle = \langle S ( I_{i}(t)) \rangle
\end{equation}

**The motivation for mean-field analysis** [1]
The motivation for mean field analysis comes from problem faced when we wish to evalutate (3). The component $$I_{syn}(t)$$ in $$I_{ext}(t)$$ depends on the state of each of the neighboring neurons of i at each point in time. This mean, when we wish to evaluate (3), we must account for all the states of each neighbor including their probalities of being in a particular state and the effect of being in that state that it has on neuron i. Concretely, let $$x(t)$$ represent the vector of states of all neigbors of neuron i. Then we can rewrite (2) and (3) as follows:
\begin{equation}
f_{i}(t) = S ( I_{i}(x(t)))
\end{equation}
\begin{equation}
\langle f_{i}(t) \rangle = \langle S ( I_{i}(x(t))) \rangle = \sum_{x}S(I_{i}(x(t)p(x(t)))
\end{equation}
where $$p(x(t))$$ is the probaility that the neigbors are in state $$x$$

## Example 1: Binary Neurons

## Example 2: LIF Neurons

## Example 3: Mean-field Approximation in a Model of Visuospatial Working Memory

## References
