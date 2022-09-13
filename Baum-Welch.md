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
It is computed inductively in a similar manner to the [[Forward Algorithm]] ^BackwardProb

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

Let $\upxi_{t}$ be the probability of being in state $i$ at time $t$ and state $j$ at time $t+1$, given the observation sequence and the model:
$$
\upxi_{t}(i,j) = P(q_{t}=i, q_{t+1}=j | O,\lambda)
$$

To compute $\upxi_{t}$, we first compute a probability which is similar to $\upxi_{t}$, but differs in including the probability of the observation:
$$
\tilde{\upxi_{t}}(i,j) = P(q_{t}=i, q_{t+1}=j,O|\lambda)
$$

![[Computation_of_Joint_Prob.png]]

The figure shows the various probabilities that need to be combined to produce $P(q_{t}=i,q_{t+1}=j,O|\lambda)$:
- $\alpha_{t}(i)$ - Likelihood of being in state $i$, after observations $o_{1}, \dots,o_{t}$ from the [[Forward Algorithm]] (*getting there*)
- $a_{ij}$ - Current transition probability from state $i$ to state $j$ (*transitioning states*)
- $b_{j}(o_{t+1})$ - Observation probability of symbol $o_{t+1}$ at state $j$ (*emitting symbol*)
- $\beta_{t+1}(j)$ - Probability of seeing observations $o_{t+1},\dots,o_{T}$, given in state $j$ from the [[Baum-Welch#^BackwardProb|Backward probability]] (*going forward*)

These four are multiplied together to produce $\tilde{\upxi}_t$ as follows:
$$
\tilde{\upxi_{t}}(i,j) = \alpha_{t}(i)a_{ij}b_{j}(o_{t+1})\beta_{t+1}(j)
$$
To compute $\upxi_{t}$ from $\tilde{\upxi_{t}}$, we follow the laws of probability. Since,
$$
P(X|Y,Z) = \frac {P(X,Y|Z)}{P(Y|Z)} 
$$
we divide $\tilde{\upxi_{t}}$ by $P(O|\lambda)$:
$$
{\frac{\tilde{\upxi_{t}}(i,j)}{P(O|\lambda)}} = \frac{P(q_{t}=i, q_{t+1}=j,O|\lambda)}{P(O|\lambda)} = P(q_{t}=i, q_{t+1}=j|O,\lambda) = \upxi_{t}(i,j)
$$
The probability of the observation given the model is simply the forward probability of the whole utterance (or the backward probability of the whole utterance):
$$
P(O|\lambda) = \sum\limits_{j=1}^{N}\alpha_{t}(j)\beta_{t}(j)
$$
The final equation for $\upxi_{t}(i,j)$ is:
$$
\upxi_{t}(i,j) = \frac{\alpha_{t}(i)a_{ij}b_{j}(o_{t+1})\beta_{t+1}(j)}{\sum\limits_{j=1}^{N}\alpha_{t}(j)\beta_{t}(j)}
$$
To get the total expected number of transitions from state $i$, we can sum over all transitions out of state $i$. Therefore, the final formula for $\hat{a}_ij$ is:
$$
\hat{a_{ij}}= \frac {\sum\limits_{t=1}^{T-1} \upxi_{t}(i,j)}{\sum\limits_{t=1}^{T-1} \sum\limits_{k=1}^{N}\upxi_{t}(i,k)}
$$
### Observation Probability

