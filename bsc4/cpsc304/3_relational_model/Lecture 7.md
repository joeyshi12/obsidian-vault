---
course: "cpsc304"
lecture: 7
---

## SQL DDL
Write the SQL DDL for the following one-to-one relation

![[Pasted image 20220929155110.png]]

```SQL
CREATE TABLE Country(
    country-name CHAR(20) PRIMARY KEY,
    capital-name CHAR(20),
    UNIQUE capital-name -- needed for one-to-one constraint
```

[[L7 Clicker 3]]

## Translating Weak Entities

![[Pasted image 20220929160932.png]]
- Include both partial keys and owner primary key as primary key in schema
- If owner is deleted, weak entities are deleted
```SQL
CREATE TABLE Dep_Insurance (  
    pname CHAR(20),  
    age INTEGER,  
    cost REAL,  
    ID CHAR(11)  
    PRIMARY KEY (ID, pname),  
    FOREIGN KEY (ID) REFERENCES MoviePeople,  
    ON DELETE CASCADE)
```

## Translating ISA
- 

## Translating Aggregation
![[Pasted image 20220929162354.png|800]]
