---
course: CPSC304
title: Views
topic: View
tags: View
module: 6
date: [[2022-11-15]]
---

## Example

**Tables**:
- Course(Course\#, title, dept)
- Enrolled(Course\#, sid, mark)

```SQL
Create View CourseWithFails(dept, course#, mark) AS
SELECT C.dept, C.course#, mark
FROM Course C, Enrolled mark
FROM Course C, Enrolled E
WHERE C.course# = E.course# AND mark < 50
```