---
course: "cpsc304"
topic: "Entity Relationship Model"
lecture: 2
---

## Levels of Abstraction
- **External / View level**: describes different parts of the database to different users
    - e.g., UBC view for student grades and classes
- **Conceptual / Logical level**: how data is perceived by the users

![[Pasted image 20220913153555.png|300]]


## Schema and Instances
- The logical structure of the database (e.g., students take courses
- Later we'll populate instances - the content of the database at a particular point in time
    - e.g., currently there are no grades for CPSC 304


## Conceptual Database Design
- What are the entities and relationships in the enterprise?
    - Entities are usually nouns
        - e.g., students and courses
    - Relationships are statements about 2 or more objects. Often verbs.
        - e.g., a prof teaches a course
- What information about these entities and relationships should we store in the database?
- What integrity constraints or other rules hold?
- In relational databases, this is encoded in an **Entity-Relationship (ER) Diagram**


## ER Model Basics
- **Entity**: Real-world object that is distinguishable from other objects
- An entity is described using a set of attributes
- **Entity Set**: A collection of similar entities
    - All entities in an entity set have the same set of attributes (with ISA as an exception)
    - Each attribute has a **domain** (e.g.., float, date, int)  
    - Each entity set has a key. The key is composed of all  underlined attributes

![[Pasted image 20220913154756.png|400]]

## Keys
- Used to distinguish entities
- A key is the **minimal set** or one or more attributes which, taken collectively, identify uniquely an entity in an entity set
- A primary key is the key chosen as the principal means to identify entities in an entity set
- The only keys shown in ER diagrams are primary keys
- We'll discuss superkeys when we consider normal forms

**Clicker Question**: If SIN and Student ID both can uniquely identify a student entity, SIN + Student ID is not a possible key!
- SIN + Student ID is **NOT A MINIMAL SET**

- **Relationships**: Association among two or more entities
    - e.g., Michelle Yoh worked on "Everywhere Anywhere All at Once"
- **Relationship Set** Collection of similar relationships.
    - Collection of all movie People that have worked in movies
- Same entity set could participate in different relationship sets, or in different “roles” in same set. (Kirk Douglas isParentOf Michael Douglas)  

![[Pasted image 20220913161046.png|500]]

![[Pasted image 20220913164055.png|400]]


## Notation
- **Entity**: Rectangle (has attributes, relationships)
- **Attribute**: Ellipse
- **Primary key**: Underlined (main key for identifying)
- **Relationship**: Diamond (connects with 2 entities and an attribute)
    - Course and student gives grade
## Cardinalities
- A cardinality ratio for a relationship set specifies the number of relationships in the set that an entity can participate in

Let $R$  be a relationship set between $A, B$. $R$ can have 1 of 4 cardinalities
1. One-to-one from $A$ to $B$
2. One-to-many from $A$ to $B$
    - An entity in $A$ is associated with any number of entities in $B$
    - An entity in $B$ is associated with at most one entity in $A$
    - e.g., A biological mother to children
3. Many-to-one from $A$ to $B$
4. Many-to-many from $A$ to $B$