---
course: "cpsc304"
title: "Minimal Cover"
topics: ["Normal Forms", "3NF", "Normal Form Decomposition"]
module: 4
lecture: 10
date: [[2022-10-11]]
---

## Determine the Minimal Cover
Minimal cover $G$ for a set of FDs $F$:
- $F^{+} = G^{+}$
- RHS of each FD in $G$ is a single attribute
- If we delete an FD in G or delete attributes from an FD in G, the closure changes

1. Put FDs in standard form
    - One attribute on RHS
2. Minimize LHS of each FD
3. Delete redundant FDs

```
Given:
-----
A -> B
ABCD -> E
EF -> G
EF -> H
ACDF -> EG

Step 1:
-----
A -> B
ABCD -> E
EF -> G
EF -> H
ACDF -> E } split
ACDF -> G }

Step 2:
-----
A -> B
ACD -> E
EF -> G
EF -> H
ACDF -> E
ACDF -> G

Step 3:
-----
A -> B
ACD -> E
EF -> G
EF -> H

Done.
```

