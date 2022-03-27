**inode**
- File Size
- File's on-disk metadata
- **Address** of indirect block

**vnode**
- In-memory cache of associated file's inode

**openFileTableEntry**
- File Offset

**superblock**
- Metadata for entire file system

**fileDescriptorTable**
- Mapping from file descriptor to open file table entry

**disk**
- Mapping from file offset to disk block
- Mapping from symbolic name to file metadata
