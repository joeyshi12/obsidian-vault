---
course: "cpsc313"
title: "x86, Page Faults, and Segfaults"
---


## x86 Page Table Wrap Up
- Page tables are the data structure that maps from virtual addresses to physical addresses
- x86-64 implements 4-level page tables to conserve memory
- While a complete flat page table would require 512 GB of memory, a tiny process can make do with far less using 4-level page tables


## Virtual Memory System Faults
- Page Fault:
    - Virtual page being accessed is a **valid** page, but it is not in memory.
        - Does the process get to keep running? Yes!
        - How?
            - The OS interprets the PTE
            - It brings the page into memory
            - It updates the PTE
- Segmentation Violation/Segfault:
    - The virtual page being accessed is **not valid**
        - Does the process get to keep running? No!
        - Why?
            - There is nothing that the OS can do
            - The process has requested a non-existent object
            - There is no way for the OS to signal that the 'load instruction' should return an error.
        - What does the operating system do?
            - Kills the process.


## Page Fault
1. Interpret the PTE to determine if virtual address is valid
2. See if the page is present
3. If not, find a free physical page
4. Place page contents into page (find from disk or fill with 0)
5. Fill in PTE (present bit)
6. Restart instruction
   
## Review questions
1. cr3 must contain a physical address
    1. It is needed to translate a virtual address to a physical one
    2. It cr3 contained a virtual address, how would it translate that address?
2. The size of a single page table is 4kB
    1. Each page table has 512 entries
    2. Each entry is 64 bits
3. PTEs contain physical page numbers
    1. Since we must use the PTEs during address translation, if they contained virtual addresses, we might find ourselves in an infinite loop trying to trying to translate addresses
4. PTEs do not need an offset