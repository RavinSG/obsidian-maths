---
aliases: [particular, general]
tags: []
---

# Particular and General Solution

Consider the system of equations,
$$
\begin{bmatrix}1 & 0 & 8 & -4 \\ 0 & 1 & 2 & 12\end{bmatrix} \begin{bmatrix}x_{1} \\ x_{2} \\ x_{3} \\ x_{4} \end{bmatrix} = \begin{bmatrix}42 \\ 8\end{bmatrix}
$$
The system has two equations and four unknowns. Therefore, in general we would expect infinitely many solutions.

A solution can be found immediately by taking 42 times the first column and 8 times the second column so that,
$$
b = \begin{bmatrix}42 \\ 8\end{bmatrix} = 42\begin{bmatrix}1 \\ 0\end{bmatrix} + 8 \begin{bmatrix}0 \\ 1\end{bmatrix}
$$
Therefore, a solution is $[42, 8, 0, 0]^{\top}$. This solution is called a *particular solution* or *special solution*.

However, this is **not the only solution** of this system of linear equations. To capture all the other solutions, we need to be creative in generating 0 in a non-trivial way using the columns of the matrix.

To do so, we express the third column using the first two columns so that $0 = 8c_{1} + 2c_2 - 1c_3 + 0c_4$ and $(x_{1},x_{2},x_{3},x_{4})=(8,2,-1,0)$. In fact, any scaling of this solution by $\lambda_{1} \in \mathbb{R}$ produces the $0$ vector,
$$
\begin{bmatrix}1 & 0 & 8 & -4 \\ 0 & 1 & 2 & 12\end{bmatrix} \left(  \lambda_{1}\begin{bmatrix}8 \\ 2 \\ -1 \\ 0\end{bmatrix} \right) = \lambda_{1}(8c_{1} + 2c_2 - c_{3)}= 0
$$
Following the same line of reasoning, we express the fourth column of the matrix using the first 2 columns,
$$
\begin{bmatrix}1 & 0 & 8 & -4 \\ 0 & 1 & 2 & 12\end{bmatrix} \left(  \lambda_{2}\begin{bmatrix}4 \\ 12 \\ 0 \\ -1\end{bmatrix} \right) = \lambda_{2}(4c_{1} + 12c_2 - c_{4)}= 0
$$
for any $\lambda_{2}$. Putting together, we obtain all solutions of the equation system, which is called the *general solution*.
$$
\left\{ x \in \mathbb{R}: x = \begin{bmatrix}42 \\ 8 \\ 0 \\ 0\end{bmatrix} + \lambda_{1}\begin{bmatrix}8 \\ 2 \\ -1 \\ 0\end{bmatrix} + \lambda_{2}\begin{bmatrix}-4 \\ 12 \\ 0 \\ -1\end{bmatrix}, \lambda_{1},\lambda_{2}\in \mathbb{R}
\right\}
$$
