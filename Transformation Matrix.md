---
aliases: []
tags: []
---

# Transformation Matrix

>[!tip] Definition - Transformation Matrix
>Consider vector spaces $V,W$ with corresponding (ordered) bases $B=(b_{1}, \dots ,b_{n})$ and $C = (c_{1},\dots ,c_{m})$. Moreover, we consider a linear mapping $\Phi: V \rightarrow W$. For $j \in \{1, \dots,n\}$, 
>$$
>\Phi(b_{j}) = \alpha_{1j}c_{1} + \dots + \alpha_{mj}c_{m} = \sum\limits^{m}_{i=1} \alpha_{ij}c_{i}
>$$
>is the unique representation of $\Phi(b_{j})$ with respect to $C$. Then we call the $m \times n$-matrix $A_{\Phi}$, whose elements are given by
>$$
>A_{\Phi}(i,j) = \alpha_{ij}
>$$ 
>the transformation matrix of $\Phi$ (with respect to the ordered bases $B$ of $V$ and $C$ of $W$).

The coordinates of $\Phi(b_{j})$ with respect to the ordered basis $C$ of $W$ are the $j$-th column of $A_{\Phi}$.

If $\hat{x}$ is the coordinate vector of $x \in V$ with respect to basis $B$ and $\hat{y}$ the coordinate vector of $y=\Phi(x)$ with respect to $C$, then
$$
\hat y = A_{\Phi}\hat x
$$



