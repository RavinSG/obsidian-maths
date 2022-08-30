---
aliases: []
tags: []
---

# Vector Spaces

[[Groups]]

We will consider sets that in addition to an inner operation $+$ also contain an outer operation $\cdot$, the multiplication of a vector $x \in \mathcal{G}$ by a scalar $\lambda \in \mathbb{R}$.

We can think of the *inner operation* as a form of *addition*, and the *outer operation* as a form of *scaling*

>[!tip] Definition - Vector Space
>A real-valued vector space $V = (\mathcal{V},+,\cdot)$ is a set $\mathcal{V}$ with two operations,
>$$
>\begin{align*}\\
>+ &: \mathcal{V} \times \mathcal{V} \rightarrow \mathcal{V}\\
\cdot &:\mathbb{R} \times \mathcal{V} \rightarrow \mathcal{V}
\end{align*}
>$$
>where, 
>1. $(\mathcal{V}, +)$ is an [[Abelian Group]]
>2. Distributivity:
>	1. $\forall \lambda \in \mathbb{R},x,y \in \mathcal{V}: \lambda \cdot(x + y) = \lambda \cdot x + \lambda \cdot y$
>	2. $\forall \lambda, \psi \in \mathbb{R}, x \in \mathcal{V}: (\lambda+\psi)\cdot x = \lambda \cdot x + \psi \cdot x$
>3. Associativity (outer operation): $\lambda,\psi \in \mathbb{R},x\in\mathcal{V}:\lambda\cdot(\psi\cdot x)=(\lambda\psi)\cdot x$
>4. Neutral element with respect to the outer operation: $\forall x \in \mathcal{V}: 1\cdot x=x$

The elements $x \in {V}$ are called vectors.

- [[Vector Subspaces]]
- [[Linear Independence]]






