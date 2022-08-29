---
aliases: []
tags: []
---

# Reduced Row-Echelon Form

An equation system is in reduced reduced row-echelon form if,
- It is in row-echelon form
- Every pivot is 1
- The pivot is the only nonzero entity in its column

Eg:
$$
\begin{bmatrix}\bf{1} & 3 & 0 & 0 & 3 \\ 0 & 0 & \bf{1} & 0 & 9 \\ 0 & 0 & 0 & \bf{1} & -4\end{bmatrix}
$$
The reduced row echelon form makes it easier to express non-pivot columns as a linear combination of pivot columns. 
$$
\left\{ x \in \mathbb{R}: x = \lambda_{1}\begin{bmatrix}3 \\ -1 \\ 0 \\ 0 \\ 0 \end{bmatrix} + \lambda_{2}\begin{bmatrix}3 \\ 0 \\ 9 \\ -4 \\ -1\end{bmatrix}, \lambda_{1} ,\lambda_{2} \in \mathbb{R}\right\}
$$
