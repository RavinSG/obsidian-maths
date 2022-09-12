---
aliases: [HMM, HMMs]
tags: []
---

# Hidden Markov Models

A [[Markov Chain]] is useful when we need to compute a probability for a sequence of observed events.

In many cases, however, the events we are interested in are *hidden*: we don't observe them directly.

A **hidden Markov model (HMM)** allows us to talk about both *observed* events (words that we see in the input) and *hidden* events (part-of-speech tags) that we think of as casual factors in our probabilistic model.

>[!tip] Definition - Hidden Markov Model
>An HMM is specified by the following components:
>$$
>\begin{align*}Q = q_{1},q_{2},\dots,q_{N}\ \ \ \ \ & \text{a set of N states}\\
A = a_{11},\dots a_{ij}, \dots, a_{NN}\ \ \ \ \ & \text{a transition probability matrix $A$, each $a_{ij}$ reprenting}\\
& \text{the probability of moving from state $i$ to state $j$, }\\ & \text{s.t. $\sum\limits_{j=1}^{N}a_{ij}=1 \forall i$}\\
O = o_{1},o_{2},\dots,o_{T} \ \ \ \ \ & \text{a sequence of $T$ obeservations}\\
B=b_{i}(o_{t}) \ \ \ \ \ & \text{a sequence of obsersavation likehoods, also called }\\
& \text{emmision probabilities, each expressing the }\\
& \text{probability of an observation $o_{t}$ beign generated }\\
& \text{from a state $i$} \\
\pi = \pi_{1},\pi_{2},\dots,\pi_{N} \ \ \ \ \ & \text{an initial probability distribution over states. $\pi_{i}$ is the }\\
& \text{probability that the Markov chain will start in state $i$.} \\
&\sum\limits_{i=1}^{n}\pi_{i}=1
\end{align*}
>$$

With a first-order Markov chain, the probability of a particular state depends only on the previous state. ([[Markov Assumption]])

The probability of an output observation $o_{i}$ depends only on the state that produced the observation $q_{i}$ and not on any other sates or any other observations. ([[Output Independence]])

Markov models can be characterised by three fundamental problems:
- *Likelihood* - Given an HMM $\lambda=(A,B)$ and an observation sequence $O$, determine the likelihood $P(O|\lambda)$ ^LikelihoodCalculation
- *Decoding* - Given an observation sequence $O$ and an HMM $\lambda=(A,B)$, discover the best hidden state sequence $Q$ ^DecodingTask
- *Learning* - Given an observation sequence $O$ and the set of states in the HMM, learn the HMM parameters $A$ and $B$
