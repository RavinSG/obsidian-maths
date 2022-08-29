---
aliases: []
tags: []
---

# Row-Echelon Form

>[!tip] A matrix is in row-echelon form if,
>- All rows that contain only zeros are at the bottom of the matrix; correspondingly, all rows that contain at least one nonzero element are on top of rows that contain only zeros. 
>- Looking at nonzero rows only, the **first nonzero numbe**r from the left (also called the pivot or the leading coefficient) is always **strictly to the right** of the **pivot of the row above** it.

The *leading coefficient of a row*  (first nonzero number from the left) is called the **pivot** and is always strictly to the right of the pivot of the row above it. 

Therefore, any equation system in row-echelon form always has a “*staircase*” structure.

The *variables corresponding to the pivots* in the row-echelon form are called *basic variables* and the *other variables* are *free variables*. 

The row-echelon form makes easier when we need to determine a [[Particular and General Solution|particular solution]].

To do this, we express the right-hand side of the equation system using the pivot
columns, such that $\mathit{b} = \sum_{i=1}^{P}\lambda_{i}p_{i}$, where $p_{i}, i =1, \dots,P$ are the pivot columns. 

The $\lambda_i$ are determined easiest if we start with the rightmost pivot column and work our way to the left

If we consider the following matrix in the row-echelon form,
$$\begin{align*}
&x_1&-2x_{2}&+x_{3}&-x_4&+x_{5}&= &0\\
&&&x_3&-x_4&+3x_5&=&-2\\
&&&&x_{4}&-2x_5&=&1\\
&&&&&0 &=&a+1
\end{align*} \Longleftrightarrow 
\begin{bmatrix}1 & -2 & 1 & -1 & 1 \\ 0 & 0 & 1 & -1 & 3 \\ 0 & 0 & 0 & 1 & -2 \\ 0 & 0 & 0 & 0 & 0\end{bmatrix}
$$
$$
\lambda_{1}\begin{bmatrix}1 \\ 0 \\ 0 \\ 0\end{bmatrix} + \lambda_{2}\begin{bmatrix}1 \\ 1 \\ 0 \\ 0\end{bmatrix} + \lambda_{3}\begin{bmatrix}-1 \\ -1 \\ 1 \\ 0\end{bmatrix} = \begin{bmatrix}0 \\ -2 \\ 1 \\ a+1\end{bmatrix}
$$
Only for $a=-1$ this system can be solved.

[[Reduced Row-Echelon Form]]