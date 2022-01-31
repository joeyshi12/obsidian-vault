# Riemann-Stieltjes Integral (Def. 6.2)

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
\overline{\int_a^b} f(x) d\alpha &= \inf_P U(P, f, \alpha) \\
\underline{\int_a^b} f(x) d\alpha &= \sup_P L(P, f, \alpha)
\end{align*}
$$

We say $f$ is **Riemann-Stieltjes Integrable** with respect to $\alpha$ on $[a, b]$ if $\overline{\int_a^b} f(x) d\alpha = \underline{\int_a^b} f(x) d\alpha = \int_a^b f(x) d\alpha$. We write this statement as $f\in\mathcal{R}_{\alpha}[a,b]$.

The case of $\alpha(x) = x$ is the [[Riemann Integral]]

## Theorem 6.5
$$\underline{\int_{a}^{b}} f(x) dx \leq \overline{\int_{a}^{b}} f(x) dx$$

## Theorem 6.6
$$f\in\mathcal{R}_{\alpha}[a, b] \iff \forall \epsilon > 0,\, \exists P_{\epsilon},\, s.t.\, U(P_{\epsilon}) - L(P_{\epsilon}) < \epsilon$$