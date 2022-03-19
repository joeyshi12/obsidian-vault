---
course: "cpsc313"
title: "Naming"
---

The problem to solve is reading the inode given a pathname

## Basic Ideas
Directory
- normal file (with directory type) containing list of entries `dirent`

Directory Entry
- maps a file name to its inumber

Hierarchical naming
- Directory has sub-directories
- File uniquely named by pathname

We iterate over dirents to find inumber from pathname.

![[Drawing 2022-03-18 14.13.54.excalidraw]]

## Directory Entry Struct
```C
// If inode numbers are 32 bits
struct dirent {  
ino_t d_ino;  
__uint16_t d_reclen; // total length of struct including the padding
__uint8_t d_type;  
__uint8_t d_namlen;  
char d_name[256];  
};  

// If inode numbers are 64 bits
struct dirent {  
__uint64_t d_ino;  
__uint16_t d_reclen;  
__uint16_t d_namlen;  
__uint8_t d_type;  
char d_name[1024];  
};
```

## Hard Links
Creating a file creates a link between its name and inode.
Adding a hard link `ln <target> <newName>` creates an additional name for the file.
- inode's are reference counted (`ls -l`)

What is the link count of a directory that
- is empty?
    - 2 itself and `.`
- contains 3 subdirectories?
- 5