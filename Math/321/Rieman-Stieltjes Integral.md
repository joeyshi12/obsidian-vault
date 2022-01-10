# Riemann-Stieltjes Integral

The Riemann-Stieltjes Integral is an extension of the [[Riemann Integral]]. Let $\alpha: [a, b]\to\mathbb{R}$ be a monotonically increasing function and $\Delta\alpha_i = \alpha(x_i) - \alpha(x_{i-1})$.

As with the [[Riemann Integral]], we define the following:
$$
\begin{align*}
U(P, f, \alpha) &= \sum_{i=1}^n M_i\Delta\alpha_i \\
L(P, f, \alpha) &= \sum_{i=1}^n m_i\Delta\alpha_i \\
\end{align*}
$$

$$
\begin{align*}
\overline{\int_a^b} f(x) dx &= \sup_P U(P, f, \alpha) \\
\underline{\int_a^b} f(x) dx &= \inf_P L(P, f, \alpha)
\end{align*}
$$

We say $f$ is **Riemann-Stieltjes Integrable** with respect to $\alpha$ on $[a, b]$ if $\overline{\int_a^b} f(x) dx = \underline{\int_a^b} f(x) dx = \int_a^b f(x) dx$. We write this statement as $f\in\mathcal{R}_{\alpha}[a,b]$.

