---
aliases: []
tags: []
---

# Linear Independence

>[!tip] Definition - Linear Combination
Consider a vector space $V$ and a finite number of vectors $x_{1}, \dots,x_{k}\in V$. Then, every $\mathcal{v} \in V$ of the form
>$$
\mathcal{v} = \lambda_{1}x_{1}+\dots+\lambda_{k}x_{k}=\sum_{i=1}^{k}\lambda_{i}x_{i}\in V 
>$$
>with $\lambda_{1},\dots,\lambda_{k} \in \mathbb{R}$ is a *linear combination* of the vectors $x_{1}, \dots,x_{k}$

>[!tip] Definition - Linear (In)dependence
>Let us consider a vector space $V$ with $k\in\mathbb{N}$ and $x_{1}, \dots,x_{k}\in V$. If there is a non-trivial linear combination, such that $0 = \sum\limits_{i=1}^{k}\lambda_{i}x_{i}$ with at least one $\lambda_{i}\neq 0$, the vectors $x_{1}, \dots,x_{k}$ are *linearly dependent*. 
>If only the trivial solution exists, i.e., $\lambda_{1}=\dots=\lambda_{k}=0$ the vectors $x_{1}, \dots,x_{k}$ are *linearly independent*.

Intuitively, a set of *linearly independent vectors* consists of vectors that **have no redundancy**, i.e., if we remove any of those vectors from the set, we will lose something.

A practical way of checking whether vectors $x_{1}, \dots,x_{k}\in V$ are linearly independent is to use Gaussian elimination: Write all vectors as columns of a matrix A and perform Gaussian elimination until the matrix is in row echelon form.

- The pivot columns indicate the vectors, which are linearly independent of the vectors on the left. Note that there is an ordering of vectors when the matrix is built.
- The non-pivot columns can be expressed as linear combinations of the pivot columns on their left. For instance, the row-echelon form
$$
\begin{bmatrix}1 & 3 & 0 \\ 0 & 0 & 2\end{bmatrix}
$$
	tells us that the first and third columns are pivot columns. 

---
Consider a vector space $V$ with $k$ independent vectors $b_{1},\dots,b_{k}$ and $m$ linear combinations
$$
\begin{align*}
x_{1}=& \sum\limits_{i=1}^{k}\lambda_{i1}b_{i}\\
&\vdots\\
x_m=&\sum\limits_{i=1}^{k}\lambda_{im}b_{i}
\end{align*}
$$
Defining $B = [b_{1},\dots,b_k]$ as the matrix whose columns are the linearly independent vectors $b_{1},\dots,b_k$, we can write
$$
x_{j}= B \lambda_{j}, ~~~~ \lambda_{j}= \begin{bmatrix}\lambda_{1j} \\ \vdots  \\ \lambda_{kj}\end{bmatrix}, ~~~j=1,\dots,m
$$
in a more compact form.

We want to test whether $x_{1},\dots,x_{m}$ are linearly independent. For this purpose, we follow the general approach of testing when $\sum\limits_{j=1}^{m}\psi_{j}x_{j}=0$. We can obtain,
$$
\sum\limits_{j=1}^{m}\psi_{j}x_{j}= \sum\limits_{j=1}^{m}\psi_{j}B \lambda_{j}= B\sum\limits_{j=1}^{m}\psi_{j}\lambda_j
$$
This means that ${x_{1},\dots,x_{m}}$ are linearly independent if and only if the column vectors ${\lambda_{1},\dots,\lambda_m}$ are linearly independent.
