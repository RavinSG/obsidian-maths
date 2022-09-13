---
aliases: [Forward-Backward]
tags: []
---

# Baum-Welch

During training, we *do not know* the counts of being in any of the *hidden states*. The Baum-Welch algorithm solves this by iteratively estimating the counts.

It will *start with an estimation* for the transition and observation probabilities and then use these estimated probabilities to derive better probabilities.

This is done by *computing the forward probability* for an observation and then *dividing* that probability mass *among* all the different *paths that contributed* to this forward probability.

## Backward Probability
The backward probability $\beta$ is the probability of seeing the observation from time $t+1$ to the end, given that we are in state $i$ at time $t$:
$$
\beta_{t}(i) = P(o_{t+1}, o_{t+2},\dots , o_{T}|q_{t}=i,\lambda)
$$
It is computed inductively in a similar manner to the [[Forward Algorithm]]

- ### Initialisation
$$
\beta_{T}(i) = 1, \ \ \ 1 \le i \le N
$$
- ### Recursion
$$
\beta_{i}(i) = \sum\limits_{j=1}^{N}a_{ij}b_{j}(o_{t+1}\beta_{t+1}(j)), \ \ \ 1 \le i \le N , 1 \le t < T
$$
- ### Termination
$$
P(O|\lambda) = \sum\limits_{j=1}^{N}\pi_{j}b_{j}(o_{1})\beta_{1}(j) 
$$
![[Backward_Induction_Step.png]]

Next we will see how the forward and backward probabilities can help computer the transition probability $a_{ij}$ and observation probability $b_{i}(o_{t})$ from an observation sequence without knowing the actual path taken by the model.

## Transition Probability Estimation

We can estimate $\hat{a_{ij}}$ by a variant of simple maximum likelihood estimation:
$$
\hat{a_{ij}} = \frac{\text{expected number of transitions from state $i$ to state $j$}}{\text{expected number of transitions from state $i$}} 
$$
But, we do not know the value of the numerator. To calculate it, assume we had some estimate of the probability that a given transition $i \rightarrow j$ was taken at a particular point in time $t$ in the observation sequence.

If we knew this probability for each particular time $t$, we could sum over all times $t$ to estimate the total count for the transition $i \rightarrow j$.