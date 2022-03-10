---
course: "cpsc313"
title: "File System"
plid: "P18"
---

## File System APIs
**Privilege Levels**
- Processor has at least 2 different modes of operation
    - User mode: how all regular programs run
    - Kernel/supervisor mode: how the OS runs
- The mode determines which instructions can be executed and what memory locations can be accessed

If a program cannot do something in user mode, it needs to ask the kernel to perform activities on its behalf => **System Calls**

File system APIs are implemented as library functions (in `libc`) that invoke system calls.
- **open**: returns file descriptor (fd) for accessing the file for a given a pathname
- **close**: uses a fd and frees all OS and library resource that have been allocated to it
- **read**: reads data from file referenced by fd into user-specified buffer
- **write**: takes data from buffer and writes to file referenced

```C
/*
 * @param oflag: 1. how to access (readonly, writeonly, read&write etc...),
 *               2. behaviour if file does/doesn't exist (create file, create file only if no other process is creating at the same time)
 *               3. how should file behave w.r.t. caching (sync, direct)
 * @param mode: if file does not exist and you create it, what should its access mode be set to (e.g. rwxrwxrwx = 100 000 010 = 402)
 * @return: a file descriptor/non-negative int on success; -1 on error
 */
int open(const char *path, int oflag, int mode)

/*
 * @param fd: file descriptor to be closed
 * @return: 0 on success; -1 on error
 */
int close(int fd)

/*
 * @param fd
 * @param buf: buffer into which the bytes read are placed
 * @param nbyte: number of bytes to read
 * @return: 1. success: number of bytes read
 *          2. end-of-file: 0
 *          3. failure: -1
 */
ssize_t read(int fd, void *buf, size_t nbyte)

/*
 * @param fd
 * @param buf: buffer into which the bytes to be written are placed
 * @param nbyte: number of bytes to write
 * @return: 1. success: number of bytes written
 *          2. failure: -1
 */
ssize_t write(int fd, void *buf, size_t nbyte)
```

## Disks
I/O Bridge: communicates data between processors (System bus) and devices (IO bus)
Host bus adapter: adapts data for different devices

![[Pasted image 20220308171418.png|700]]

Disk contains a platters
Platter contains data on their  top+bottom surfaces
Surface data on platter are organized into tracks/multiple concentric circles
Tracks are divided into sectors (disk blocks)

![[Pasted image 20220308171824.png|700]]

Arm

![[Pasted image 20220309010300.png]]