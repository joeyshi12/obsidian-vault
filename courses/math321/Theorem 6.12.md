# Theorem 6.12 (a)
Suppose $f_1, f_2, f_3\in\mathcal{R}_\alpha [a, b]$. Then $f_1 + f_2\in\mathcal{R}_{\alpha}[a, b]$  and $cf\in\mathcal{R}_{\alpha}[a, b]$ for all $c\in\mathbb{R}$, and $\int_{a}^{b} (f_1 + f_2) d\alpha = \int_{a}^{b} f_1 d\alpha + \int_{a}^{b} f_2 d\alpha$ and $\int_{a}^{b} (cf) d\alpha = c\int_{a}^{b} f d\alpha$.

# Theorem 6.12 (b)
If $f_1, f_2\in\mathcal{R}_{\alpha}$ and $f_1(x) \leq f_2(x)$ for all $x\in[a,b]$, then $\int_a^b f_1 d\alpha \leq \int_a^b f_2 d\alpha$

**Proof**:
$L(P , f_1, \alpha) \leq L(P, f_2, \alpha)$ for all $P$, so
$$\int_a^b f_1 d\alpha = \sup_P L(P, f, \alpha) = \sup_P L(P, f_2, \alpha) = \int_a^b f_2 d\alpha$$

## Theorem 6.12 (c)
If $f\in\mathcal{R}_\alpha[a, b]$ and $c\in(a, b)$, then
$f\in\mathcal{R}_\alpha[a, c]\cap \mathcal{R}_{\alpha}[c, b]$ and
$$\int_a^b f d\alpha = \int_a^c f d\alpha + \int_c^b f d\alpha$$

**Proof**: exercise

## Theorem 6.12 (d)
If $f\in\mathcal{R}_\alpha[a, b]$ and $|f(x)| \leq M$ for all $x\in [a, b]$,
then $|\int_a^b fd\alpha| \leq M[\alpha(b) - \alpha(a)]$

**Pf**:  Let $P = \{a, b\}$. Then,
$$-M[\alpha(b) - \alpha(a)] \leq m_1\Delta\alpha_1 \leq \int_a^b f d\alpha \leq M_1\Delta\alpha_1 \leq M(\alpha(b) - \alpha(a))$$