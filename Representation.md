---
aliases: []
tags: []
---

# Representation

Probabilistic graphical models are graphs in which nodes represent random variables, and the (lack of) arcs represent conditional independence assumptions. Hence they provide a *compact representation of joint probability distributions*.

**Undirected graphical models**, also called *Markov Random Fields* (MRFs) or *Markov networks*, have a simple definition of independence: two (sets of) nodes A and B are conditionally independent given a third set, C, if all paths between the nodes in A and B are separated by a node in C.

**Directed graphical models** also called [[Bayesian Networks]] or *Belief Networks*(BNs), have a more complicated notion of independence, which takes into account the directionality of the arcs.

In addition to the graph structure, it is necessary to *specify the parameters* of the model. For a *directed model*, we must specify the *Conditional Probability Distribution* (CPD) at each node.

If the variables are *discrete*, this can be represented as a *table* (CPT), which lists the probability that the child node takes on each of its different values for each combination of values of its parents.

Consider the following example, in which all nodes are binary, i.e., have *two possible values*, which we will denote by T (true) and F (false).

![[Conditional_Probability_Table.png]]^waterSprinkler

We see that the event "grass is wet" (W=true) has two possible causes: either the water sprinkler is on (S=true) or it is raining (R=true).

The strength of this relationship is shown in the table. For example, we see that $Pr(W=true | S=true, R=false) = 0.9$, and hence, $Pr(W=false | S=true, R=false) = 1 - 0.9 = 0.1$, since each row must sum to 1.

By the chain rule of probability, the joint probability of all the nodes in the graph above is,
$$
P(C, S, R, W) = P(C) * P(S|C) * P(R|C,S) * P(W|C,S,R)
$$

By using conditional independence relationships, we can rewrite this as,
$$
P(C, S, R, W) = P(C) * P(S|C) * P(R|C) * P(W|S,R)
$$

where we were allowed to simplify the third term because *R is independent of S given its parent C*, and the last term because *W is independent of C given its parents S and R*.

We can see that the conditional independence relationships allow us to represent the joint more compactly. 

If we had n binary nodes, the full joint would require $O(2^n)$ space to represent, but the factored form would require $O(n \cdot 2^k)$ space to represent, where k is the maximum fan-in of a node.

Fewer parameters makes learning easier.