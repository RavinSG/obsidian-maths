---
aliases: []
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





