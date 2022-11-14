---
course: CPSC304
title: Student SQL Exercises
topic: Exercises
tags:
module: 6
date: [[2022-11-01]]
---

## Table Definitions
1. Class(name, meets_at, room, fid)
2. Student(snum, sname, major, standing, age)
3. Enrolled(snum, cname)
4. Faculty(fid, fname, deptid)

Find the departments that have at least one faculty member
```SQL
SELECT DISTINCT deptid FROM Faculty;
```

Find the departments with more than one faculty member
```SQL
SELECT DISTINCT f1.deptid
FROM Faculty f1, Faculty f2
WHERE f1.deptid = f2.deptid AND f1.fid <> f2.fid
```

Find all students enrolled in a course with 'System' in the name
```SQL
SELECT DISTINCT snum
FROM enrolled
WHERE cname LIKE '%System%'
```
Do we need DISTINCT? Yes; same student can enroll in more than 1 course

Using [[Nested Queries]], find the sids of all students who took Operating System Design
but did not take Database Systems.
```SQL
SELECT sid
FROM Enrolled
WHERE cname = 'Operating System Design' AND
      snum NOT IN (SELECT snum
                   FROM Enrolled
                   WHERE cname = 'Database Systems')
```

Find the name and age of the oldest students
```SQL
SELECT sname, age
FROM Student S
WHERE NOT EXISTS (SELECT *
                  FROM Student S2
                  WHERE S2.age > S.age)
```

Find the name and age of the oldest students
```SQL
SELECT sname, age
FROM Student S
WHERE S.age >= ALL (SELECT age
                    FROM Student S2)

SELECT sname, age
FROM Student
WHERE age = (SELECT MAX(S2.age) FROM Student S2)
```

Find average age of SR students
```SQL
SELECT AVG(S2.age)
FROM Student S2
WHERE S2.standing = 'SR'
```

How many students have taken a class with "Database" in the title
```SQL
SELECT COUNT(DISTINCT snum)
FROM Enrolled
WHERE cname LIKE '%Database%'
```

Find the age of the youngest student who is at least 19, for each major
```SQL
SELECT major, MIN(age)
FROM Student
WHERE age >= 19
GROUP BY major
```

For each class, find the age of the youngest student who has enrolled in this class
```SQL
SELECT cname, MIN(age)
FROM Student S, Enrolled E
WHERE S.snum = E.snum
GROUP BY cname
```

For each course with more than 1 enrollment, find the age of the youngest student who has taken this class
```SQL
SELECT cname, MIN(age)
FROM Student S, Enrolled E
WHERE S.snum = E.snum AND C > 1
GROUP BY cname
HAVING COUNT(*) > 1
```