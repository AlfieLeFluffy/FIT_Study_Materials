---
tags:
  - IOS
aliases:
  - file system
---
- A [[File]] is a basic organizational unit for **storing data** on external [[Memory]] devices.
- A **file system** is a summary of rules, behaviour and properties of **files** and options of logical organization of **files**. A file system also defines the way in which data are stored and what information gets stored with them.
	- **[[File Allocation Table|FAT]]** is an universal file system that allows [[Operating Systems]] to share files.
	- **EXT** is a file system used for Linux.
	- **[[New Technology File System|NTFS]]** is a file system used for Windows.
## Storage
There are two common storage types are [[Hard Disk]] and [[Solid State Drive]]. Other storage types include for example [[Magnetic Tape Storage]].
## Systems
Organization and description of files should be implemented in a way that it should **minimalize overhead** while working with it and it should be **simple** to:
- **Go through a File**, which is tied to way of finding the next block.
- **Moving of Files** which is tied with the way of finding the first and a specific file block.
- **Expanding and Contracting a File** which is tied to adding and removing of blocks.
Examples of these systems are:
- [[UNIX]]
- [[Continual Storage]]
- [[Linked Block List]]
- [[File Allocation Table]]
- [[B+ Tree]]
- [[Extend]]
- [[Extend Tree]]
- [[New Technology File System
## Organization of Free Space
Free space can be organized and addressed through:
- A **bit array map** that with one bit per one block, which can be searched through with bit masking
- A **linking** of free blocks
- A **linking of link in a [[File Allocation Table|FAT]]**, that link to free blocks
- A [[B+ Tree]] which can address through size or offset
- By [[Extend]]
## Deduplication
**Restriction of repeated storing** of same data on either the file, extent, block byte level. This can save space for example on email servers that can receive one mail for hundreds of recipients, git repositories and so on. This can be implemented in **writing** or **additionally**, and uses cryptographic hashing for searching for a match. A problem arises once one of the shared files is updates, which requires for the file to be duplicated and one of the updated. With small duplication this can increased [[Microprocessor|CPU]], time or space consumption.
## Adding Disks
A new disk and other devices can be added to any directory of an already existing file system. Today most of all [[Operating Systems]] automatically mounts disks after connecting them to the PC.
### Virtual File System (VFS)
Creates a unified interface for work with different file systems. This separates the higher level of an [[Operating Systems]] from the specific implantation of individual file system operations in individual file systems.
### Network File System (NFS)
Makes available files stored on different systems. This is connected/integrated into **VFS** and working with it for the [[Operating Systems]] and the user is identical to working with files on a disk.
### Spooling
Is the simultaneous peripheral operations on-line. It allows to speed up of slow output devices such as when printing through a printer. The outcome is done into a file and a process, that started the operation can continue. The created file is saved into a queue of requests to the output device (printer) and waits for its turn.