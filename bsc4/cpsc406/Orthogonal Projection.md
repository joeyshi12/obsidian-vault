---
course: CPSC406
title: Orthogonal Projection
tags: []
date: [[2023-01-12]]
---

![[Orthogonal Projection 2023-01-12 11.29.28.excalidraw]]

$\overline{y} = \text{proj}_{\mathcal{L}}(b) = \arg\min \{\|y - b\| \mid y\in{\mathcal{L}}\}$
$\overline{r} = \text{proj}_{\mathcal{L}_{ortho}}(b) = \arg\min \{\|r - b\| \mid r\in{\mathcal{L}_{ortho}}\}$

Orthogonal projection: $b = \overline{y} + \overline{r}$,  $\overline{y}^T\overline{r} = 0$

In particular, we can consider the case of $\mathcal{L} = \text{range}(A)$ (column span) to get the least squares problem.
$\overline{y} = Ax_{LS}$

$$
\begin{align*}
\overline{r}\in\text{range}(A)_{orthogonal}
&= \{z \mid y^Tz = 0, y\in{\text{range(A)}}\} \\
&= \{z \mid (Ax)^Tz = 0, x\} \\
&= \{z \mid x^TA^Tz = 0, x \} \\
&= \{z \mid A^Tz = 0\} \\
&= \text{null}(A^T)
\end{align*}
$$

$$
\begin{align*}
A^T\overline{r} = 0 &\Rightarrow A^T(b - Ax_{LS}) = 0 \\
&\Rightarrow A^TAx_{LS} = A^Tb, \quad [\text{Normal equations}]
\end{align*}
$$
Note: $\text{rank}(A) = m \Rightarrow \text{rank}(A^TA) = m \Rightarrow A^TA \text{ invertible}$

To prove uniqueness, we show that a perterbation from $\overline{y}$ in the linear subspace reduces the optimality.

![[Orthogonal Projection2 2023-01-12 11.29.28.excalidraw]]

$x_{LS} = (A^TA)^{-1}A^Tb$
$\overline{y} = Ax_{LS} = A(A^TA)^{-1}A^Tb = Pb$, where
$P = A(A^TA)^{-1}A^T$

Define a matrix $P$ (in general) to be the orthogonal projector onto range($P$) if
1. $P = P^2$ (idempotent)
2. $P = P^T$ (symmetric)

We confirm that $\overline{y}^T\overline{r} = 0$
$$
\begin{align*}
\overline{y}^T\overline{r} &= (Pb)^T(b - Pb) \\
&= b^TP^Tb - b^TP^TPb \\
&= b^TPb - b^TPPb \\
&= b^TPb - b^TP^2b \\
&= 0
\end{align*}
$$