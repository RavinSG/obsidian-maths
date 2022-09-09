---
aliases: [homomorphism]
tags: []
---

# Linear Mappings

Consider two real vector spaces $V,W$. A mapping $\Phi : V \rightarrow W$ preserves the structure of the vector space if 
$$
\begin{align*}
\Phi(x+y) &= \Phi(x) + \Phi(y)\\
\Phi(\lambda x) &= \lambda\Phi(x)
\end{align*}
$$
for all $x,y \in V$ and $\lambda \in \mathbb{R}$.

>[!tip] Definition - Linear Mapping
>For vector spaces $V, W$ a mapping $\Phi :V\rightarrow W$ is called a *linear mapping* (or vector space homomorphism/ linear transformation) if,
>$$
\forall x,y \in V \ \forall \lambda ,\psi \in \mathbb{R}: \Phi(\lambda x + \psi y) = \lambda\Phi(x) + \psi\Phi(y)
>$$

Linear mappings can also be presented as matrices (see ..). 

>[!tip] Definition - Injective, Surjective, Bijective
>Consider a mapping $\Phi:\mathcal{V} \rightarrow \mathcal{W}$, where $\mathcal{V},\mathcal{W}$ can be arbitrary sets. Then $\Phi$ is called
>- *Injective* if $\forall x,y \in \mathcal{V} :\Phi(x) = \Phi(y) \Longrightarrow x = y$
>- *Surjective* if $\Phi(\mathcal{V}) = \mathcal{W}$
>- *Bijective* if it is injective and surjective

- If $\Phi$ is surjective, every element in $\mathcal{W}$ can be "reached" from $\mathcal{V}$ using $\Phi$
- A bijective $\Phi$ can be "undone", i.e., there exists a mapping $\Psi: \mathcal{W} \rightarrow \mathcal{V}$ so that $\Psi \circ \Phi(x) = x$. This mapping $\Psi$ is then called the inverse of $\Phi$ and normally denoted by $\Phi^{-1}$ 

## Special Cases of Linear Mappings
- *Isomorphism*: $\Phi:V\rightarrow W$ linear and bijective
- *Endomorphism*: $\Phi:{V}\rightarrow {V}$ linear
- *Automorphism*: $\Phi:{V}\rightarrow {V}$ linear and bijective
- *Identity mapping* or identity automorphism in $id_{V}:V\rightarrow V, x \mapsto x$ 


>[!note] Theorem 
>Finite-dimensional vector spaces $V$ and $W$ are isomorphic if and only if $$dim(V)=dim(W)$$^Theorm2-17

This states that there exists a linear, bijective mapping between two vector spaces of the same [[Basis|dimension]].

It also justifies to treat $\mathbb{R}^{m\times n}$ (the vector space of $m \times n$ matrices) and $\mathbb{R^{mn}}$ (the vector space of length $mn$) the same, as their dimensions are $mn$, and there exists a linear, bijective mapping that transforms one into the other.

>[!example] Remark
>- For linear mappings $\Phi: V \rightarrow W$ and $\Psi: W \rightarrow X$, the mapping $\Psi \circ \Phi: V \rightarrow X$ is also linear
>- If $\Phi:V \rightarrow W$ is an isomorphism, then $\Phi^{-1}:W \rightarrow V$ is an isomorphism, too
>- If $\Phi: V \rightarrow W, \Psi: V \rightarrow W$ are linear, then $\Phi + \Psi$ and $\lambda\Phi, \lambda \in \mathbb{R}$ are linear too

[[Matrix Representation of Linear Mappings]]


