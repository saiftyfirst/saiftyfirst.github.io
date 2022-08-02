---
layout: page
title:  "Mean-field Approximation"
date:   2022-07-26 20:29:32 +0200
categories: jekyll update
---
### Introduction
Mean-field approximation is technique that can be used to study the approximate dynamics of a Markov population process, given that the size of the population is large enough. Generally, this is carried out by reducing/representing the system as a system of differential equations. [1]

**Definition - Overall mean-field model** [1]
An overall mean-field model, $$X$$, describes the limit behaviour of N->$$\infty$$; individual objects, each modelled by *X*, and is defined as a tuple $$(X,Q)$$, that consists of an infinite set of states:
$$X = \{ \overline{x} = (x_1,x_2,..,x_K)(\forall j\in \{1,...,K\},x_j\in[0,1] \wedge \sum^K_{i=1}x_i=1) \}$$
where $$\overline{x}$$ is called occupancy vector and $$\overline{x}(t)$$ is the value of the occupancy vector at time t; $$x_j$$ denotes the fraction of the individual objects that are in state $$s_j$$ of the local model *X*. The transition rate matrix $$Q(\overline{x}(t))$$ consists of entries $$Q_{s,s`}$$ that describe the transition from state $$s$$ to $$s`$$.

**Theorem - Mean-field convergence theorem** [1]
The normalized occupancy vector $$\overline{x}(t)$$ at time $$t$$ < $$\infty$$ tends to be deterministic un distribution and satisfies the following differential equation when $$N$$ tends to infinity
$${d\overline{x}(t)}/{dt}=\overline{x}(t).Q(\overline{x}(t))$$ given $$\overline{x}(0)$$.

### Mean-field approximation of binary neurons

### Mean-field approximation of LIF neurons

### Mean-field Approximation in a Model of Visuospatial Working Memory
In [2], we can find an example of the mean field approximation applied to a model of Visuospatial Working Memory. Here, the single neuron is modeled by its firing rate, r, and its dynamics are given by the following differential equation:
$$\tau_0 dr/dt=-f(r) + g(I)$$ , where $$\tau_0$$ is the chrracteristic time of the cell, and the functions $$f(r)$$ and $g(I)$$ represent the instrinsic properties of the neuron which depend on the firing rate, r, and the input drive, I, respectively. 






### References

