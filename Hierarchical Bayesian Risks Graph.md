---
aliases: [HBRG]
tags: []
---

# Hierarchical Bayesian Risks Graph

The HBRG is a hierarchical model of three layers combined [[Bayesian Risks Graph]]. 

![[Hierarchical_Bayesian_Risk_Graph_Model.png]]

The above image shows a typical HBRG model that consists a BN model at each layer.

A risk-evaluation process performs at each layer and a compound risk evaluation will be given for each app (or system).

A HBRG can be represented with $<\mathbf{G}_{HBRG},\mathbf{R}>$  in which,
1. $\mathbf{G}_{HBRG} = \{G_{S}, G_{D}, G_{B}\}$ denotes the BRGs model, in which $G_S$ denotes the BRG at *static layer*, $G_D$ denotes the BRG at *dynamic layer*, and $G_B$ denotes the BRG at *behavioural layer*, respectively. The relationships among random variables at each node are constrained by the model structure and a directed acyclic graph (DAG) obeying the usual conditional independence assumptions. Specifically, the arcs between the BRG nodes represent probabilistic causal dependencies.
2. Relation $\mathbf{R}$, a key concept of the HBRN model, provides the bridge among the layered BRG. $\mathbf{R}$ is a set of association $\{R_{ij}|(i=1,2,\dots ,m); j\in (1,2,\dots,n\}$ with $R_{ij}=1$ implying that node $S_{i}$ is assign to state $true$ of relationship with node $S_{j}$  

