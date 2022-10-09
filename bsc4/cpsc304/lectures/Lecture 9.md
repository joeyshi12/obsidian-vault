---
course: "cpsc304"
lecture: 9
---

## Exercise 1
Given relationship R(A, B, C, D, E) and FDs
- AB -> C
- CD -> E
- BE -> A
Take the closure of the functional depenencies

Solution:
- AB+ = ABC
- CD+ = CDE
- BE+ = BEAC


## Lossless-Join Decompositions: Definition
- Decomposition of R into X and Y is lossless-join w.r.t. a set of FDs F if, for every instance r that satisfies F:  
    - If we JOIN the X-part of r with the Y-part of r the result is exactly r


## Lossy-Join Decomposition
![[Pasted image 20221006155110.png|800]]


## How to decompose into BCNF losslessly?
- Let R be a relation with attributes A, and FD be a set of   FDs on R s.t. all FDs determine a single attribute  
    1. Pick any $f \in FD$ that violates BCNF of the form $X\to b$  
    2. Decompose R into two relations: R1($A-b$) & R2($X \cup b$)  
        - Recurse on R1 and R2 using FD
        
![[Pasted image 20221006155454.png]]


## BCNF Example 1
- Relation R(ABCD), FD: B -> C, D -> A
- B+ = {B, C}
- D+ = {A, D}
- BD+ = {B,C,A,D}

BD is the only key

BCNF is violated since B is not a superkey (B -> C is a non-trivial relation and B is not a superkey)
Decompose: ( AD (B) C ) => R1(B, C) R2(A, B, D)
- R1 is in BCNF because it has 2 attributes
- D -> A in R2 violates BCNF => decompose ( B (D) A  )
    - R3(D, A), R4(D, B)

    
## BCNF Example 2
Find closure of
- R(ABCDE), FD: AB -> C, D -> E

AB+ = {A, B, C}
D+ = {D, E}

BCNF is violated
- Decompose AB (DE (AB) C)
    - R1(A, B, C), R2(A, B, D, E)
    - D is not a key for R2 => Not in BCNF
    - R3(A, B, D), R4(D, E)


## BCNF Example 3
A+ = ABC
DE+ = DEF
B+ = BC

Decompose on A -> B: (CDEF (A) B)
- R1(ACDEF), R2(AB)
- Decompose on DE -> F: (AC (DE) F)
    - R3(DEF), R4(ACDE)
    - On R4, B doesn't exist, so A+ = {A, C}
    - Decompose on A -> C: (DE (A) C)
        - R5(A, C) R6(D,E,A) -> R7 R8
        

R(ABCDE), S(ABCD)
- AB -> C
- BC -> D
- CD -> E
- DE -> A
- AE -> B

E does not exist in S:
- BCD+ = {BCDEA} (BCD -> A holds in S)

FD is trivial if closure is the LHS

R(ABCD)
- A -> B
- C -> D
- AD -> C
- BC -> A

- Decompose R: (CD (A) B) => R1(AB), R2(CDA)
- Decompose R2: (A(C)D) => R3(CD), R4(AC)


## 3NF
A relation R is in 3NF if
- X -> b is a non-trivial dependency in R, then X is a superkey for R
- **OR b is part of a (minimal) key**


## How do we find minimal keys?
R(ABCD), where AB -> C and C -> BD
1. List all attributes that only appear on the RHS
    - D
2. List attributes that only appear on the LHS of a FD
    - These items cannot be derived from other (must appear in minimal key)
    - A
3. List attributes that appear on LHS and RHS of FDs
    - BC
4. Take the closure of the attributes in the left column
    - A+ = {A}
5. Add attributes in middle
    - AB+ = ABCD <- minimal key
    - AC+ = ACBD <- minimal key