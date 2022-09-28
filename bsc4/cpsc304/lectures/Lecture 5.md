---
course: "cpsc304"
topic: "The Relational Model"
lecture: 5
---

## Logical Schema Representation Specs
- Ability to store data - w/o worrying about blocks on disk
- Ability to query data easily
- A representation that is easy to understand
- A representation that we can easily adapt from conceptual schema
- Separate from application programming language


## Key Points of Relational Model
- Simple to understand - main abstraction represented as a table
- **Physical Data Independence** - ability to modify physical schema w/o changing logical schema
- **Logical Data Independence** - done with views
    - Ability to change the conceptual schema without changing applications


## Structure of Relational Databases
- **Relational database**: a set of **relations**
- **Relation**: made of 2 parts:
    - **Schema**: specifies name of relation, plus name and domain (type) of each attribute
        - e.g., Student (sid: string, name: string, address: string, phone: string, major: string)
        - Instance : a table, with rows and columns.
        - \# Rows = cardinality
        - \# Columns = arity / degree
- **Relational Database Schema**: collection of schemas in the database
- **Database Instance**: a collection of instances of its relations


## SQL Examples
- Creates the Student relation
```sql
--Creates student relation
CREATE TABLE Student  
    (sid INTEGER,  
    name CHAR(20),  
    address CHAR(30),  
    phone CHAR(13),  
    major CHAR(4))

--Destroys the relation Student
DROP TABLE Student

--adding a new attribute
ALTER TABLE Student  
    ADD COLUMN gpa REAL

--Can insert a single tuple
INSERT  
INTO Student (sid, name, address, phone, major)  
VALUES (‘52033688’, ‘G. Chan’, ‘1235 W. 33, Van’,  
‘882-4444’, ‘PHYS’)

--Can delete all tuples satisfying some condition
DELETE  
FROM Student  
WHERE name = ‘Smith’
```


## Key Constraints (for Relations)
- One or more attributes in a relation form a **key** (or **candidate key**) for a relation, where S is the set of all attributes in the key if:
    1. No distinct tuples can have the same values for all attributes in the key, and
    2. No subset of S is itself a key (accroding to (1))
- One of the possible keys is chosen (by the DBA) to be the **primary key**
- Superkeys uniquely identifies entity, but not necessarily minimal

```sql
CREATE TABLE Student  
    (sid INTEGER PRIMARY KEY,  
    name CHAR(20),  
    address CHAR(30),  
    phone CHAR(13),  
    major CHAR(4))
```

**Primary key constraints**
- Values for primary key must be unique
- A primary key attribute cannot be null
- Other keys are specified using the `UNIQUE` constraint
    - Values for a group of attributes must be unique (if they are not null)
    - These attributes can be null
- Key constraints are checked when
    - New values are inserted
    - Values are modified