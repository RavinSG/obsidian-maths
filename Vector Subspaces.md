---
aliases: []
tags: []
---

# Vector Subspaces

Intuitively, they are *sets contained in the original vector space* with the property that when we perform *vector space operations on elements* within this subspace, we *will never leave it*.

>[!tip] Definition - Vector Subspace
> Let $V = (\mathcal{V},+,\cdot)$ be a vector space and $\mathcal{U} \subseteq \mathcal{V} \neq \emptyset$. Then $U = (\mathcal{U},+,\cdot)$ is called vector subspace of $V$ (or linear subspace) if $U$ is a vector space with the vector space operations $+$ and $\cdot$ restricted to $\mathcal{U}\times\mathcal{U}$ and $\mathbb{R}\times\mathcal{U}$.
> We write $U \subseteq V$ to denote a subspace $U$ of $V$.

If $\mathcal{U} \subseteq \mathcal{V}$ and $V$ is a vector space, then $U$ naturally inherits many properties
directly from $V$ because they hold for all $x \in\mathcal{V}$, and in particular for all $x \in \mathcal{U} \subseteq \mathcal{V}$.

To determine whether $(\mathcal{U},+,\cdot)$ is a subspace of $V$ we still do need to show,
1. $\mathcal{U} \neq \emptyset$, in particular: $0 \in \mathcal{U}$
2. Closure of $U$
	- With respect to the outer operation: $\forall \lambda \in \mathbb{R} \space \forall x \in \mathcal{U}:\lambda x \in \mathcal{U}$  
	- With respect to the inner operation: $\forall x,y \in \mathcal{U}: x + y \in \mathcal{U}$

>[!info] Remark
>Every subspace $U \in (\mathbb{R}, +, \cdot)$ is the solution space of a [[Homogeneous Linear Equations|homogeneous]] system of linear equations $\mathbf{A}x = 0$ for $x \in \mathbb{R}^n$

