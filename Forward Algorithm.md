---
aliases: [likelihood]
tags: []
---

# Forward Algorithm

The forward algorithm is kind of a dynamic programming algorithm that stores intermediate results.

The forward algorithm computes the observation probability by summing over the probabilities of all possible hidden state paths that could generate the observation sequence, but it does so efficiently by implicitly folding each of these paths into a
single *forward trellis*.

![[Forward_Algorithm.png]]

The figure shows the computation of $\alpha_{t}(j)$ for two states at two time steps. The computation in each cell follows 
$$
\alpha_{t}(j) = \sum\limits _{i=1}^{N}\alpha_{t-1}(i)a_{ij}b_j(o_t)
$$
The resulting 