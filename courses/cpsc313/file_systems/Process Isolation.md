---
course: "cpsc313"
title: "Process Isolation"
---

- Programs run in different **processes**
- Each process has its own **address space**
- Address spaces provide **process isolation**
- Process isolation means:
    - Anything one process does should not affect what another process does, unless the processes agree (e.g., set up a communication channel)
    - Each process behaves as if it controls the entire machine's resources
