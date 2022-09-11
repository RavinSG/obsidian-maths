---
aliases: [HMM, HMMs]
tags: []
---

# Hidden Markov Models

A [[Markov Chain]] is useful when we need to compute a probability for a sequence of observed events.

In many cases, however, the events we are interested in are *hidden*: we don't observe them directly.

A **hidden Markov model (HMM)** allows us to talk about both *observed* events (words that we see in the input) and *hidden* events (part-of-speech tags) that we think of as casual factors in our probabilistic model.
