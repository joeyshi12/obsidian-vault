---
course: "cpsc313"
title: "Virtual Memory"
---

## Big Picture
- What is the purpose of virtual memory?
    - It provides process isolation
- How does VM work?
    - Hardware/software partnership
    - The hardware translates whatever addresses it can, using some combination  of TLB (translation look-aside buffer) and page table. That is, specific  processors might have only a TLB; others might have both a TLB and the ability to ‘walk’ a page table.

## VM Mapping
**Basic Idea**
- $(va, access, priv) \Rightarrow pa | FAULT$
- $pa$ are not contiguous
- Avoid fragmentation

## Pages
- Vitual pages and physical pages are the same size
    - Virtual page size is set by hardware
    - Maximum size of virtual address space is determined by hardware
    - Therefore, the number of bits or size of a virtual page number is also determined by the hardware
- The max number of physical pages is also determined by hardware
- The actual number of phycial pages is specific to a particular machine
- Virtual page numbers and physical page numbers can be different sizes

## Represent Sparse Address Space
- Think of virtual address space as a sparse file

## Implementing this is HW
- **Guiding principles**:
    - Using bit values directly is good, cheap, simple
    - Computing things is relatively slower and more expensive
    
## From file index to a a page table
1. Instead of an **inode**/index, we have a hardware register: **CR3**
2. Everything used to call indirect blocks, we call **page tables** (L1 page table, L2 page table)
    - Page table entry contains **PPN**, **present bit**, **permissions**
    - PTE may point to a page/data or another PTE
3. The x86-64 has 4-levels of page tables
4. All page tables are indexed by bits in the virtual address

## Why are 36 bits reserved?
- 4KB page size means pages table is 4KB. Each entry is 8B, so 9 bits are needed to index into a page table
- 4 levels in x86-64
- Therefore, 36 bits is exactly how many bits needed to index into a page

## X86 Address Summary
- 16 bit unused
- 36 bit for L1, L2, L3, L4 page table indices
- 12 bits for offset