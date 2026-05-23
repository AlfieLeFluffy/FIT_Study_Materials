---
tags:
  - IOS
aliases:
  - unix
sources:
---
Unix FS is the simplest division of the disk. For this is uses several types of blocks:
- **Boot Block** is the first block in the logical addressing. It contains information necessary to boot up (initiate) the [[Operating Systems]].
- **Super Block** is the second block in the logical addressing. It contains information about the file system such as type, size, number of 1-nodes, number of empty i-nodes, root directory, UUID, etc.
- **Table of I-nodes** are block directly after the Super block and contain the table of i-nodes.
- **Data Blocks** after the table of i-nodes are the data blocks which continue until the end of the disk. They contain either file data or indirect links.
There are couple of possible upgrades to this such as:
- The disk is divided into **groups of blocks**, with each group having its own i-nodes table, data block and empty blocks. This allows for better space managment and data locality.
- Super block containing the information about the file system is stored several types to avoid issues if it was damaged or faulty. Pretty much the same idea as RAID 1.
### I-node
An i-node is a basic data structure that describe files in UNIX style file systems. These nodes contain metadata and in special cases data about files. This metadata can include:
- **State of the i-node** (allocated, free, ...)
- **File Type** (normal, directory, device, etc.)
- **File Length in Bytes**
- **mtime** time of last modification
- **atime** time of access
- **ctime** time of creation
- **UID** identification of ownership
- **GID** identification of group
- **Access Rights**
The i-node **does not contain the name of the file**. The data itself is linked to via:
- **10 Direct** links, which is quick but only for small files
- **1 Indirect** link of the **first degree**
- **1 Indirect** link of the **second degree** (links to a block that directs to blocks of first degree)
- **1 Indirect** link of the **third degree** (links to a block that directs to blocks of second degree)
Based on the **size of each block** and the size of **links in one block** we can calculate the maximum size of file in this file system as:
```
10 * D + N * D + N^2 * D + N^3 * D
```
where the number of links in a block **N** is **D / M**, which is the size of one block **D** (commonly 4096B) and the size of one link **M** (commonly 4B). This is also influenced by the [[Operating Systems]].