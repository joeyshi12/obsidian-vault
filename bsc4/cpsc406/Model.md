A model is an abstraction of a process
- Parameters $x = (x_1,\dots, x_n)\in\mathcal{P}$
- Prediction $m(x)\in\mathcal{F}$

![[Model 2023-01-10 11.12.16.excalidraw]]

## Mathematical Optimization
- The optimal value:
$$p^* = f(x^*) = \min_{x\in\mathcal{C}} f(x)$$
- Optimal solution set:
$$\mathcal{S} := \{x\in\mathcal{C} \mid p^* = f(x)\}$$
- Reveal Data:
$$p^*(b) = \min_{x\in\mathcal{C}} f(x; b)$$

**Note:** Assume $f$ is differentiable on the nonempty interior of the fesible set $\mathcal{C}\subseteq \mathbb{R}^n$.
$$
\nabla f(x) =
\begin{pmatrix}
\frac{\partial f(x)}{\partial x_1} \\
\vdots \\
\frac{\partial f(x)}{\partial x_n}
\end{pmatrix}
$$