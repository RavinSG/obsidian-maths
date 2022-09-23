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

The above theorem tells that with a basis change in $V$ and $W$, the transformation matrix $A_{\Phi}$ of a linear mapping $\Phi: V \rightarrow W$ is replaced by an equivalent matrix $\tilde{A}_{\Phi}$ with
$$
\tilde{A}_{\Phi}= T^{-1}A_{\Phi}S
$$

![[Basis_Change_Transformation.png]]

We can express a linear mapping $\Phi_{\tilde{C}\tilde{B}}$ as a composition of linear mappings that involve the "old" basis:
$$
\Phi_{\tilde{C}\tilde{B}} = \Upxi_{\tilde C C} \ \circ \Phi_{CB} \ \circ \Psi_{B\tilde B} = \Upxi_{C\tilde C}^{-1} \ \circ \Phi_{CB} \ \circ \Psi_{B\tilde B}
$$
Concretely, we use $\Psi_{B\tilde B} = id_{V}$ and $\Upxi_{C\tilde C} = id_{W}$, i.e. the identity mappings that map vectors onto themselves, but w.r.t a different basis. 

>[!example]  Example
>Consider a transformation matrix
>$$
>A = \begin{bmatrix}2 & 1 \\ 1 & 2\end{bmatrix}
>$$
>w.r.t the canonical basis in $\mathbb{R}^2$. If we define a new basis
>$$
>B = \left(\begin{bmatrix}1 \\ 1\end{bmatrix}, \begin{bmatrix}1 \\ -1\end{bmatrix} \right)
>$$
>we obtain a diagonal transformation matrix
>$$
>\tilde{A} = \begin{bmatrix}3 & 0 \\ 0 & 1\end{bmatrix}
>$$
>w.r.t $B$, which is easier to work with than $A$.

- [[Equivalence]]
- [[Similarity]]

>[!info] Remark
>Consider vector spaces $V,W,X$. From [[Linear Mappings#^extension|this]] we know that for linear mappings $\Phi: V \rightarrow W$ and $\Psi: W \rightarrow X$, the mapping $\Psi \circ \Phi: V \rightarrow X$ is also linear. With transformation matrices $A_\Phi$ and $A_{\Psi}$ of the corresponding mappings, the overall transformation matrix is $A_{\Psi\circ\Phi} = A_{\Psi}A_{\Phi}$
>

