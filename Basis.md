---
aliases: [dimension]
tags: []
---

# Basis 

[[Generating Set and Span]]

>[!tip] Definition - Basis
>Consider a vector space $V=(\mathcal{V},+,\cdot)$ and $\mathcal{A} \in \mathcal{V}$. A [[Generating Set and Span|generating set]] $\mathcal{A}$ of $V$ is called minimal if there exists no smaller set $\tilde{\mathcal{A}} \subsetneq \mathcal{A} \subseteq \mathcal{V}$ that spans $V$. Every linearly independent generating set of $V$ is minimal and is called a basis of $V$.

We only consider finite-dimensional vector spaces $V$. The *dimension* of $V$ is the number of basis vectors of $V$, and we write $dim(V)$. 

If $U\subseteq V$ is a subspace of $V$, then $dim(U) \leq dim(V)$ and $dim(U)=dim(V)$ if and only if $U=V$.

>[!example] Remark
>A basis of subspace $U=span[x_{1},\dots,x_{2}] \in \mathbb{R}^n$ can be found by executing the following steps:
>1. Write the spanning vectors as columns of a matrix $A$
>2. Determine the row-echelon form of $A$
>3. The spanning vectors associated with the pivot columns are a basis of $U$

