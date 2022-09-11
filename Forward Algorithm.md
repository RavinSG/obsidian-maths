---
aliases: [likelihood]
tags: []
---

# Forward Algorithm

The forward algorithm is kind of a dynamic programming algorithm that stores intermediate results.

The forward algorithm computes the observation probability by summing over the probabilities of all possible hidden state paths that could generate the observation sequence, but it does so efficiently by implicitly folding each of these paths into a
single *forward trellis*.

![[Forward_Algorithm.png]]

The resulting probability expressed in each cell is $\alpha_{t}(j) = P(o_{1},o_{2},\dots ,o_{t},q_{t}=j|\lambda)$ 

The figure shows the computation of $\alpha_{t}(j)$ for two states at two time steps. The computation in each cell follows 
$$
\alpha_{t}(j) = \sum\limits _{i=1}^{N}\alpha_{t-1}(i)a_{ij}b_j(o_t)
$$
The three factors that are multiplies extending the previous paths to compute the forward probability at time $t$ are,
$$
\begin{align*}
&\alpha_{t-1}(i)&&  \text{The previous forward path probability from the previous time step}\\
&a_{ij}&& \text{The transition probability from previous state $q_{i}$ to current state $q_j$}\\
&b_{j}(o_{t})&& \text{The state observation likelihood of the observation symbol $o_t$ given}\\
&& &\text{the current state $j$} 
\end{align*}
$$
