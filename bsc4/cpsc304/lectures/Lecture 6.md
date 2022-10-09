---
course: "cpsc304"
lecture: 6
---

## Foreign Key Constraints
- **Foreign Key**: Set of attributes in one relation used to reference a tuple in another relation
    - Must correspond to the primary key of the other relation
    - Like a pointer
- e.g., Grade(sid, dept, course#, grade)
    - sid is a foreign key referring to Student:
    - (dept, course#) is a foreign key referring to Course
- **Referential integrity**: All foreign keys reference existing entities
    - i.e., there are no dangling reference
    - All foreign key constraints are enforced


## SQL Foreign Key On Update/Delete
SQL/92 supports all 4 options on deletes and updates.
- Default is NO ACTION (delete/update is rejected)
- CASCADE (also updates/deletes all tuples that refer to the updated/deleted tuple)
- SET NULL / SET DEFAULT (referencing tuple value is set to the default foreign key value )