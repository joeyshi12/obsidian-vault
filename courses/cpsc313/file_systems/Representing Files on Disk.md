---
course: "cpsc313"
title: "Representing Files on Disk"
---

![[Pasted image 20220314140503.png|700]]

## Layers of Abstraction
Application: stream of bytes

File: sequence of logic blocks, `LBN = floor(offset / file_system_block_size [or file size])`

**Disk**
- sequence of physical blocks
- a file is a collection of physical blocks
- PBN (physical block number) is computed from LBN using `inode` block map

## Data Structures & Concepts
**inode**
- on-desk metadata that describes a file
- stores a map (`LBN -> PBN`) and some other metadata
- does not have symbolic, human readable name
**inumber**
- internal "name" of an inode
- file system can map `inumber -> disk block` for that file's inode
- `ls -i` to see file inumbers
**super block** (minor)
- metadata for entire file system
- stored at specific disk locations (e.g., block #0) and replicated multiple places on disk
- to **mount** a file system OS must be able to read its super block

## Let's store something in a new file
**Steps**
- `create`: allocate a new inode thus assigni
`PBN = f(LBN) = PBN_start + LBN`

*handles sparse files poorly*

## Single-extent-based allocation