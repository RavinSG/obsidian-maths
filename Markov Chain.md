---
aliases: []
tags: []
---

# Markov Chain

A **Markov chain** is a model that tells us something about the probabilities of sequences of random variables, *states*, each of which can take on values from some set.

A Markov chain makes a very strong assumption that if we want to predict the future in the sequence all that matters is the current state. Which is known as the [[Markov Assumption]].

>[!tip] Definition - Markov Chain
>Formally, a Markov chain is specified by the following components:
>$$
>\begin{align*}Q = q_{1},q_{2},\dots,q_{N} \ \ \ \ \ \ \ & \text{a set fo N states}\\
A = a_{11},a_{12},\dots,a_{n1},\dots,a_{nm}\ \ \ & \text{a transition probability matrix A, each $a_{ij}$} \\ &\text{representing the probability of moving from} \\ &\text{ state $i$ to state $j$ s.t. $\sum\limits_{j=1}^{n}a_{ij}=1 \forall i$}\\
\pi = \pi_{1},\pi_{2}, \dots ,\pi_{N} \ \ & \text{an initial probability distribution over states.} \\ &\text{$\pi_{i}$ is the probability that the Markov Chain will} \\ &\text{ start in state $i$.} \sum\limits^{N}_{i=1}\pi_{i}=1
>\end{align*}
>$$

