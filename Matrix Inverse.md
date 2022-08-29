---
aliases: [invertible, noninvertible]
tags: []
---

# Matrix Inverse

>[!tip] Definition 
>Consider a square matrix $A \in R^{n\times n}$. Let matrix $B \in R^{n\times n}$ have the property that $AB = I_{n} = BA$. $B$ is called the inverse of $A$ and denoted by $A^{-1}$.

Not every matrix $A$ possesses an inverse $A^{-1}$. I*f this regular inverse does exist*, $A$ is called [[Regular Matrix|regular]]/[[Matrix Inverse|invertible]]/[[nonsingular]], otherwise [[singular]]/[[Matrix Inverse|noninvertible]].

$$
\mathbf{A}\mathrel{\mathop:}= \begin{bmatrix}a_{11} & a_{12} \\ a_{21} & a_{22}\end{bmatrix} \in \mathbb{R^{2 \times2}}
$$
If we multiply $\mathbf{A}$ with, 
$$
\mathbf{A'}\mathrel{\mathop:}= \begin{bmatrix}a_{22} & -a_{12} \\ -a_{21} & a_{11}\end{bmatrix}
$$
we obtain, 
$$
\mathbf{AA'} = \begin{bmatrix}a_{11}a_{22}-a_{12}a_{21} & 0  \\ 0  & a_{11}a_{22}- a_{12}a_{21}\end{bmatrix} = (a_{11}a_{22}- a_{12}a_{21}) \mathbf{I}
$$

Therefore, 
$$
\mathbf{A^{-1}} = \frac{1}{a_{11}a_{22}- a_{12}a_{21}} \begin{bmatrix}a_{22} & -a_{12} \\ -a_{21} & a_{11}\end{bmatrix}
$$
if and only if $a_{11}a_{22}-a_{12}a_{21}\neq 0$.
