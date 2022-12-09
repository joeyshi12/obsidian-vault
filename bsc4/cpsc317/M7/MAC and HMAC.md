## MAC
- $\text{MAC}(m) = H(m+s)$
- Suppose Alice sends Bob a message $m$ and hash $H(m)$ for message integrity.
- Since $H()$ is public, Trudy could send Bob $(m', H(m'))$, where $m'$ is any message.
- Let $s$ be a shared secret between Alice and Bob.
    - Now Alice sends $(m, h)$, where $h = H(m+s)$ and Bob can verify the integrity of the message by checking $H(m+s) = h$ after receiving $(m, h)$.
    - It is more difficult for Trudy to come up with the MAC since she does not have the shared secret $s$.

## HMAC
- $\text{HMAC}(m) = H(k, H(k, m))$
- Extended from MAC
- Much more secure than MAC