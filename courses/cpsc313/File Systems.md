---
course: "cpsc313"
title: "File Systems"
---

## File: stream of bytes
Reading from the file increments the current offset
- After reading 4 bytes the offset moves  by 4
- Read and write **SHARE** the same offset
- Offset indicates the next location from which to read or to which to write
- Kernel keeps track of file descriptions in array (file descriptor table)

Each open file needs an offset for reading and writing.
The file descriptor must help us find
- The file's data (PERSISTENT)
- The file's **metadata** (how large the file is, who can access the file) (PERSISTENT)
- The file offset; no file is open when system is first booted => (NOT PERSISTENT)

## Stream of bytes => blocks
A file is a stream of bytes, but

data can only be read from a disk one block/sector at a time

Reading a byte requires that we retrieve a block from the disk
- How do we find the block?

**Which block?**
`Offset / sizeof(block) = blockNumber`, but
- This is not a disk address!
- This block number is relative to the start of this file
- There are lots of files on the disk and lots of blocks/sectors as well


## File name hierarchy
- A file name of the form /A/BC/DE/file

![[Pasted image 20220309143107.png|500]]

```
// open(pathname)

Offset => Logical Block Number (LBN) => Metadata => Disk address
                                           ^
                                           |
                                        pathname
```


## File Descriptor Table

Process: program in execution
Program when running => process (address space + one or more threads of execution)

Call to open
1. Look for space available in file descriptor table
2. Initialize offset = 0 or end of file if opened with append
3. Increment refcount
4. Something with Vnode?

Open File Table entry maps one-to-one with calls to open
Vnode map table entry maps one-to-one with files

![[Pasted image 20220311140450.png|700]]

## Fork
```C
/*
 * Creates a new process *almost* identical to the process that called it
 * The parent's return value will be the pid of the child process.
 * The child process's return value will be 0
 */
pid_t fork(void)
```

Why create a duplicate process?
```C
/*
 * @param typically path is the pathname of a command you want to execute, e.g., ./myprog, /bin/ls
 * @param argv arg vector
 * @param envp environment
 */
int execve(const char *path, char *const argv[], char *const envp[])

int execvp(const char *path, char *const argv[])
```

When we call fork, we get a new descriptor table which will increment some refcounts

![[Pasted image 20220311142044.png]]

```C
// du

int dup(int fd)

//
int dup2(int fd1, int fd2)
```

```C
// Implementation of `ls > my-stdout-file.txt`

pid_t child_pid = fork();
if (child_pid == 0) {
    /* In the child. */
    int fd = open("my-stdout-file.txt", O_WRONLY|O_CREATE|O_TRUNC, 0644);
    dup2(fd, STDOUT_FILENO);
    execv("ls", argv); // Changes child to execute 'ls' instead of shell
} else if (child_pid == 0) {
    This is the parent
} else {
    This is an error
}
```