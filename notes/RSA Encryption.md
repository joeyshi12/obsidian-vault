# RSA Encryption
- $c \equiv m^e\pmod{n}$
- $\gcd(e, \phi(n)) = 1$

Since $\gcd(e, \phi(n)) = 1$, there exists a solution $d$ of $ed = 1\pmod{\phi(n)}$

Thus, $c^d = (m^e)^d = m^{k\phi(n) + 1} \equiv m\pmod{n}$ for some $k\in\mathbb{Z}$

Hence, $m \equiv c^d\pmod{n}$