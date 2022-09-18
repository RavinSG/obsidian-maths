---
aliases: []
tags: []
---

# Representation

Probabilistic graphical models are graphs in which nodes represent random variables, and the (lack of) arcs represent conditional independence assumptions. Hence they provide a *compact representation of joint probability distributions*.

**Undirected graphical models**, also called *Markov Random Fields* (MRFs) or *Markov networks*, have a simple definition of independence: two (sets of) nodes A and B are conditionally independent given a third set, C, if all paths between the nodes in A and B are separated by a node in C.

**Directed graphical models** also called *Bayesian Networks* or [[Belief Networks]] (BNs), have a more complicated notion of independence, which takes into account the directionality of the arcs.


