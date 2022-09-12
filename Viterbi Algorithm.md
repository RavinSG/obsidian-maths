---
aliases: []
tags: []
---

# Viterbi Algorithm

Like the [[Forward Algorithm]], *Viterbi* is a kind of *dynamic programming* that makes uses of a dynamic programming trellis.

The idea is to process the observation sequence left to right, filling out the trellis. 

Each cell if the trellis, $v_{t}(j)$, represents the probability that the HMM is in state $j$ after seeing the first $t$ observations and passing through the most probable sate sequence $q_{1},\dots,q_{t-1}$, given the automaton $\lambda$.

The value of each cell $v_{t}(j)$ is computed by recursively taking the most probable path that could lead to this cell. Formally,
$$
v_{t}(j) = \max_{q_{1},\dots,q_{t-1}} P(q_{1}\dots q_{t-1},o_{1}\dots o_{t}, q_{t}=j|\lambda) 
$$

The Viterbi probability is computed by taking the most probable of the extensions of the paths that lead to the current cell.

For a given state $q_{j}$ at time $t$, the value $v_{t}(j)$ is computed as,
$$
v_{t}(j) = \max_{i=1}^{N} v_{t-1}(i)a_{ij}b_{j}(o_{t})
$$
The three factors multiplied are,
$$
\begin{align*}
&v_{t-1}(i) &&\text{the previous Viterbi path probability from the previous time step}\\
&a_{ij} &&\text{the transition probability from previous state $q_i$ to current state $q_{j}$}\\
&b_{j}(o_{t}) &&\text{the state observation likelihood of the observation symbol $o_{t}$ given the} \\
&&&\text{current state $j$}
\end{align*}
$$
The Viterbi algorithm has one component that the forward algorithm doesn't have: *backpointers* 

![[Viterbi_Algorithm.png]]

Since the algorithm must produce a probability and also the most likely state sequence, the path of hidden stated that led to each state is kept track of.

At the end, the best path is backtracked to the beginning to identify the most probable path.

- ### Initialisation
$$
\begin{align*}
v_{1}(j) &= \pi_{j}b_{j}(o_{1})  &1 \le j \le N\\
bt_{1}(j) &= 0 &1\le j \le N
\end{align*}
$$
- ### Recursion
$$
\DeclareMathOperator*{\argmax}{argmax}
\begin{align*}
v_{t}(j) &= \max_{i=1}^{N}v_{t-1}(i) a_{ij}b_{j}(o_{t}); &1 \le j \le N, 1<t\le T\\
bt_{t}(j) &= \argmax_{i=1}^{N}v_{t-1}(i) a_{ij}b_{j}(o_{t}); &1 \le j \le N, 1<t\le T
\end{align*}

$$
- ### Termination
$$
\begin{align*}
\text{The best score:}& &P^{*} &= \max_{i=1}^{N}v_{T}(i)\\
\text{The start of back trace:}& &q_{T^{*}} &= \argmax_{i=1}^{N}v_{T}(i)
\end{align*}

$$

