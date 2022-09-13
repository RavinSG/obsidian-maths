---
aliases: []
tags: []
---

# HMM Training

![[Hidden Markov Models#^HMMTraining]]

The input for a learning algorithm would be an unlabelled sequence of observations $O$ and a list of potential hidden states $Q$.

The standard algorithm for HMM training is the [[Baum-Welch|Forward-Backward]], or [[Baum-Welch]] algorithm, special case of the *Expectation-Maximisation* or *EM* algorithm.

The algorithm trains both the transition probabilities $A$ and the emission probabilities $B$ of the HMM.

EM is an *iterative* algorithm, computing an initial estimate for the probabilities, then using those estimates to computing a better estimate, and so on, iteratively improving the probabilities that it learns.

