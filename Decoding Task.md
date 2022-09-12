---
aliases: []
tags: []
---

# Decoding Task

![[Hidden Markov Models#^DecodingTask]]

For any model, such as [[Hidden Markov Models|HMM]], that contains hidden variables, the task of determining which sequence of variables is the underlying source of some sequence of observations is called the *decoding task*.

>[!tip] Definition - Decoding
>Given as input an HMM $\lambda = (A,B)$ and a sequence of observations $O=o_{1},o_{2},\dots ,o_{T}$, find the most probable sequence of states $Q = q_{1}q_{2}q_{3}\dots q_{T}$

The most common decoding algorithm for HMMs is the [[Viterbi Algorithm]]