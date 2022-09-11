---
aliases: []
tags: []
---

# Likelihood Calculation

To compute the likelihood of a particular observation.
![[Hidden Markov Models#^LikelihoodCalculation]]

For a [[Markov Chain]], where the surface observations are the same as the hidden events, we could compute the probability just by following the state and multiplying the probabilities along the arcs.

For [[Hidden Markov Models]], each hidden state produces only a single observation. Thus, the sequence of hidden states and the sequence of observations have the same length.

### Likelihood of a Sequence
Given this assumption and the [[Markov Assumption]], for a particular hidden state sequence $Q=q_{0},q_{1}q_{2},\dots ,q_{T}$ and an observation sequence $O=o_{1},o_{2},\dots,o_{T}$, the likelihood of the observation sequence is
$$
P(O|Q) = \prod_{i=1}^{T}P(o_{i}|q_{i})
$$
But, we do not know what the hidden state sequence was. Hence, we need to computer the probability of the events by summing over all possible state sequences, weighted by their probability.

###  Joint Probability
First, compute the joint probability of being in a particular sequence $Q$ and generating a particular sequence of observations $O$. This is,
$$
P(O,Q) = P(O|Q) \times P(Q) = \prod_{i=1}^{T}P(o_{i}|q_{1}) \times \prod_{i=1}^{T}P(q_{i}|q_{i-1})
$$
We can now compute the total probability of the observations by summing over all possible hidden state sequences:
$$
P(O) = \sum\limits_{Q}P(O,Q) = \sum\limits_{Q}P(O|Q)P(Q)
$$
### Time Complexity
For an HMM with $N$ hidden states and an observation sequence of $T$ observations, there are $N^{T}$ possible hidden sequences. Since this grows exponentially with the number of observations, it is not feasible to use it with long sequences. 

Instead a more efficient algorithm named the [[Forward Algorithm]] with complexity of $O(N^{2}T)$ is used.