# Riemann Integral

A **partition** of $[a, b]$ is a collection $\set{x_0,..., x_n}$, such that $a = x_0\leq x_1\leq\cdots \leq x_n = b$.

For $f: [a, b]\to\mathbb{R}$, we define the following:
$$
\begin{align*}
M_i &= \sup\{f(x) : x_{i-1}\leq x\leq x_i\} \\
m_i &= \inf\{f(x) : x_{i-1}\leq x\leq x_i\}
\end{align*}
$$

$$
\begin{align*}
U(P, f) &= \sum_{i=1}^{n} M_i \Delta x_i \\
L(P, f) &= \sum_{i=1}^{n} m_i \Delta x_i 
\end{align*}
$$

$$
\begin{align*}
\text{Upper Riemann Integral} &= \overline{\int_a^b} f(x) dx = \sup_P U(P, f) \\
\text{Lower Riemann Integral} &= \underline{\int_a^b} f(x) dx = \inf_P L(P, f)
\end{align*}
$$

We say $f$ is **Riemann Integrable** on $[a, b]$ if $\overline{\int_a^b} f(x) dx = \underline{\int_a^b} f(x) dx = \int_a^b f(x) dx$ [**Riemann Integral**]. We write this statement as $f\in\mathcal{R}[a,b]$.