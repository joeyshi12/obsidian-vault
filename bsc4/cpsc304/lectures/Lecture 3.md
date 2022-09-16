---
course: "cpsc304"
topic: "Entity Relationship Model"
lecture: 3
---


## Participation Constraints
- Pariticpation: indicates if all entities participate in the relationship.
- An entity's participation can be **total** or **partial**
- Requiring total participation is a **participation constraint** and it is *shown with a thick line*
    - Important on deletions
    - i.e., participation of Movie in Directs is total (thick line
        - Every movie must appear in some relationship in the directs sets
 
![[Pasted image 20220915160639.png|800]]


## Generalization/Specialization (ISA relationships)
- Attributes can be inherited
- If we declare A **ISA** B, every A entity is a B entity
- Parent must be on top of the triangle
- Reasons for using **ISA**:
    - To add descriptive attributes specific to a subclass
    - To restrict entities that participate in a relationship

![[Pasted image 20220915162232.png|500]]

**There are some ISA constraints we can't express in ER diagrams**
- Overlap constraints:
    - Specializations can be:
        - Disjoint: a superclass entity belongs to no more than a single subclass
        - Overlapping: subclasses may overlap
- Covering constraints :Specializations can be:  
    - Total: a superclass entity must belong to some subclass  
    - Partial: some superclass entity may not be in any subclass
 
![[Pasted image 20220915162647.png|800]]


## Weak Entities
- A **weak entity** can be identified uniquely only by additionally considering the primary key of another (owner) entity.  
    - Owner entity set and weak entity set must participate in a one-to-many relationship set (one owner, many weak entities). 
    - Weak entity set must have total participation in this identifying relationship set.  
    - Think of this as a “belongs to” relationship.  
- Weak entity sets and their identifying relationship sets are shown with thick lines.  

![[Pasted image 20220915162953.png|800]]