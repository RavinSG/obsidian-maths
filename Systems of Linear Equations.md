---
aliases: []
tags: []
---

# Systems of Linear Equations

Many problems can be formulated as systems of linear equations, and linear algebra gives us the tools for solving them

In a system of linear equations with two variables $x_1, x_2$, each linear equation
defines a line on the $x_1x_2$-plane. 

Since a solution to a system of linear equations must satisfy all equations simultaneously, the **solution set is the intersection of these lines**.

For a systematic approach to solving systems of linear equations, we will introduce a useful compact notation. We collect the coefficients $a_{ij}$ into vectors and collect the vectors into matrices

$$ 
\begin{bmatrix}a_{11} \\ \vdots \\ a_{m1}\end{bmatrix} x_{1} + \begin{bmatrix}a_{12}  \\ \vdots \\ a_{m2}\end{bmatrix} x_{2}+ \dots + \begin{bmatrix}a_{1n} \\ \vdots \\ a_{mn}\end{bmatrix} x_{n} = \begin{bmatrix}b_{1} \\ \vdots  \\ b_{m}\end{bmatrix}
\Longleftrightarrow 
\begin{bmatrix}a_{11} & \dots & a_{1n} \\ \vdots &  & \vdots \\ a_{m1} & \dots & a_{mn}\end{bmatrix} 
\begin{bmatrix}x_{1} \\ \vdots \\ x_{n }\end{bmatrix} = 
\begin{bmatrix}b_{1} \\ \vdots  \\ b_{m}\end{bmatrix}
$$

[[Matrices]]
[[Vector Spaces]]


## Solving Systems of Linear Equations

- [[Particular and General Solution]]
- [[Row-Echelon Form]]