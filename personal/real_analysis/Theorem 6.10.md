# Theorem 6.10
If $f$ is bounded on $[a, b]$ and has only finitely many discontinuities on $[a, b]$, and $\alpha$ is continuous at each point where $f$ is not, then $f\in\mathcal{R}_{\alpha}[a, b]$.

## Proof
We'll apply theorem 6.6.
Use $U(P) - L(P) = \sum_{i=1}^{n} (M_i - m_i)\Delta\alpha_{i}$.
Let $\epsilon > 0$.
Let $E = \{e_1, \dots, e_k\} =$ set of points where $f$ is discontinuous.
$\alpha$ continuous at points of $E \Rightarrow \exists$ disjoint intervals $[u_j, v_j]$
with $u_j < e_j < v_j$ (allow equality if $e_j = a$ or $e_j = b$)
and with $\alpha(v_j) - \alpha(u_j) < \epsilon$.

![[Pasted image 20220114092311.png]]

![[Pasted image 20220114093118.png]]

Let
$$K = [a, b]\cap(\cup_{j=1}^k (u_j, v_j))^C$$
which is a compact set.
$f$ is continuous on $K\Rightarrow$ uniformly continuous on $K$ (theorem 4.19),
so $\exists\delta > 0$, such that
$s, t\in k$ and $|s - t < \delta \Rightarrow |f(s) - f(t)| < \epsilon$.

For partition $P = \{x_0,\dots, x_n\}$ to consist of $\{u_1, v_1,\dots, u_k, v_k\}$ and additional points in $K$ with $\Delta x_i < \delta$.
For a subintervals in $K$, $M_i - m_i < \epsilon$.
For $(u_j, v_j)$, $M_j - m_j \leq 2M$ and $\Delta \alpha_j < \epsilon$.
$$\therefore U(P) - L(P) = \sum_{i=1}^{n} (M_i - m_i)\Delta\alpha_i
\leq k\cdot 2M\cdot \epsilon [\alpha(b) - \alpha(a)]$$
- $k\cdot 2M\cdot \epsilon$ from $(u_j, v_j)$ intervals
- $\epsilon[\alpha(b) - \alpha(a)]$ from $K$ intervals

RHS is as small as desired by taking $\epsilon$ small
$\Box$

**Notes**
- This implies A1 Q2, but you should do this from first principles
- A1 Q4 shows what can happen when $f$, $\alpha$ are discontinuous at some point.