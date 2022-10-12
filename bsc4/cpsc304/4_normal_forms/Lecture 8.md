---
course: "cpsc304"
lecture: 8
---

![[Pasted image 20221004153842.png|800]]
- Q: How many Joel Friedmans?
- Issue: The mailing address per department occurs more than once

**New tables**:
- Faculty(<u>Name</u>, <b><u>Dept name</u></b>, <b><u>Mailing location</u></b>) (encapsulate dept, mail location in Department table)
- Department(Dept name, Mailing location)


## Functional dependencies
A **functional dependency** $X\to Y$
means attribute X determines attribute Y
i.e. for any tuples `t1`, `t2`,  `t1.x = t2.x => t1.y = t2.y`

Trivial cases $(X, Y)\to X$ is obvious


## Naming the Evils of Redundancy
- Update anomaly: Need to change more than 1 thing to stay consistent.
- Insert anomaly: attributes cannot be inserted without the presence of other attributes.
- Deletion anomaly: attributes are lost because of deletion of other attributes.


## Superkeys
Recall a key is a minimal set of attributes that uniquely identify a relation
- i.e., a key is a minimal set of attributes that functionall determines all the attributes

- A superkey for a relation uniquely identifies the realtion, but does not need to be minimal


## Closure
- Attribute A always includes A
- Use list of given FD to determine closure


## Approaching Normality
- Normalization: process of removing redundancy from data
- Important normal forms
    - 1NF: First normal form
    - 2NF: second 
    - BCNF
    - 3NF


## 1NF
Each attribute in a tuple has only 1 value
![[Pasted image 20221004163314.png|800]]


## 2NF
- No partial key dependency
- A relation is in 2NF if it is in 1NF for every FD X -> Y, where X is a minimal key and Y is a non-key attribute, then non proper subset of X determines Y
    - $A\subset X$ If $X\to Y$ and $A\to Y$, then this is not in 2NF


## Boyce-Codd Normal Form (BCNF)
- R is in BCNF if
    - X -> b is a non-trivial dependency in R, then X is a superkey for R
    - i.e., whenever a set of attributes of R determine another attribute, it should determine all the attributes in R
    
