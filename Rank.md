---
aliases: [image, range]
tags: []
---

# Rank

>[!tip] Definition - Rank
>The number of linearly independent columns of a matrix $A \in \mathbb{R}^{m\times n}$ equals the number of linearly independent rows and it is called the rank of $A$ and is denoted by $rk(A)$

The rank of a matrix has some important properties:
- $rk(A) = rk(A^\top)$, i.e., the column rank equals the row rank
- The columns of $A\in \mathbb{R}^{m\times n}$ span a subspace $U \in \mathbb{R}^m$ with $dim(U)=rk(A)$.We call this subspace the *image* or *range*.
- The rows of $A\in \mathbb{R}^{m\times n}$ span a subspace $W \in \mathbb{R}^n$ with $dim(U)=rk(A)$.
- For all $A \in \mathbb{R}^{n\times n}$ it holds that $A$ is [[Regular Matrix|regular]]([[Matrix Inverse|invertible]]) if and only if $rk(A) =n$.
- For all $A \in \mathbb{R}^{m\times n}$ and all $b \in \mathbb{R}^{m}$ it holds that the linear equation system $Ax = b$ can be solved if and only if $rk(A) = rk(A|b)$, where $A|b$ denotes the augmented system.