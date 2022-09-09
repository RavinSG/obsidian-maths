---
aliases: []
tags: []
---

# Matrix Representation of Linear Mappings

We consider a basis $\{b_{1}, \dots , b_n\}$ of an $n$-dimensional vector space $V$ . In the
following, the order of the basis vectors will be important. Therefore, we
write
$$
B = (b_{1}, \dots,b_{n})
$$
>[!tip] Definition - Coordinates
>Consider a vector space $V$ and ad ordered basis $B=(b_{1},\dots ,b_{n})$ of $V$. For any $x \in V$ we obtain a unique representation (linear combination)
>$$
>x = \alpha_{1}b_{1} +\dots + \alpha_{n}b_{n}
>$$
>of x with respect to $B$. Then $\alpha_{1},\dots ,\alpha_{n}$ are the coordinates of $x$ with respect to $B$, and the vector
>$$
>\alpha = \begin{bmatrix}\alpha_{1} \\ \vdots \\ \alpha_{n}\end{bmatrix} \in \mathbb{R}^n
>$$
>is the *coordinate vector/coordinate representation* of $x$ with respect to the ordered basis $B$.

![[Two_Coordinate_Systems.png]]
Two different coordinate systems defined by two sets of basis vectors. A vector $x$ has different coordinate representations depending on which coordinate system is chosen.

>[!example] Remark
>For an $n$-dimensional vector space $V$ and an ordered basis $B$ of $V$, the mapping $\Phi: \mathbb{R}^{n}\rightarrow V, \Phi(e_{i}) = b_{i}, i = 1, \dots ,n$ is linear(from [[Linear Mappings#^Theorm2-17|Theorem]]), where $(e_{1}, \dots , e_{n})$ is the standard basis of $\mathbb{R}^n$.

[[Transformation Matrix]]
