---
aliases: []
tags: []
---

# Basis Change

We will have a closer look at how [[Transformation Matrix|transformation matrices]] of a linear mapping $\Phi : V \rightarrow W$ change if we change the bases in $V$ and $W$. Consider two ordered bases
$$
B = (b_{1},\dots,b_{n}), \ \ \ \ \tilde{B} = (\tilde{b}_{1}, \dots, \tilde{b}_{n})
$$
of $V$ and two ordered bases
$$
C = (c_{1},\dots,c_{m}), \ \ \ \ \tilde{C} = (\tilde{c}_{1}, \dots, \tilde{c}_{m})
$$
of $W$. 

Moreover, $A_{\Phi}\in \mathbb{R}^{m\times n}$  is the transformation matrix of the liner mapping $\Phi: V \rightarrow W$ w.r.t the bases $B$ and $C$, and $\tilde{A}_{\Phi}\in \mathbb{R}^{m\times n}$ is the corresponding transformation mapping w.r.t $\tilde{B}$ and $\tilde{C}$.

>[!note] Theorem - Basis Change
> For a linear mapping $\Phi: V\rightarrow W$, ordered bases
> $$
> B = (b_{1},\dots,b_{n}), \ \ \ \ \tilde{B} = (\tilde{b}_{1}, \dots, \tilde{b}_{n})
>$$
>of $V$ and
>$$
>C = (c_{1},\dots,c_{m}), \ \ \ \ \tilde{C} = (\tilde{c}_{1}, \dots, \tilde{c}_{m})
>$$
>of $W$, and a transformation matrix $A_{\Phi}$ of $\Phi$ w.r.t $B$ and $C$, the corresponding transformation matrix $\tilde{A}_{\Phi}$ w.r.t the bases $\tilde{B}$ and $\tilde{C}$ is given as
>$$
>\tilde{A}_{\Phi}= T^{-1}A_{\Phi}S
>$$
> Here, $S \in \mathbb{R}^{n\times n}$ is the transformation matrix of $id_{V}$ that maps coordinates w.r.t $\tilde{B}$ onto coordinated w.r.t. $B$, and $T \in \mathbb{R}^{m\times m}$ is the transformation matrix of $id_{W}$ that maps coordinated w.r.t $\tilde{C}$ onto coordinates w.r.t $C$. ([[Basis Change Proof|proof]])

Consider a transformation matrix
$$
A = \begin{bmatrix}2 & 1 \\ 1 & 2\end{bmatrix}
$$
w.r.t the canonical basis in $\mathbb{R}^2$. If we define a new basis
$$
B = \left(\begin{bmatrix}1 \\ 1\end{bmatrix}, \begin{bmatrix}1 \\ -1\end{bmatrix} \right)
$$
we obtain a diagonal transformation matrix
$$
\tilde{A} = \begin{bmatrix}3 & 0 \\ 0 & 1\end{bmatrix}
$$
w.r.t $B$, which is easier to work with than $A$.
