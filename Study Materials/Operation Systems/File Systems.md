- A [[File]] is a basic organizational unit for **storing data** on external [[Memory]] devices.
- A **file system** is a summary of rules, behaviour and properties of **files** and options of logical organization of **files**. A file system also defines the way in which data are stored and what information gets stored with them.
	- **FAT** is an universal file system that allows [[Operating Systems]] to share files.
	- **EXT** is a file system used for Linux.
	- **NTFS** is a file system used for Windows.
## Storage Types
There are two common storage types, which are:
### Hard Drive (HDD)
A hard drive uses several disks called platters that spin at a constant rate and head that can move from the edges of the platter to their center to read and write data to the disk. We divide the disk into **sectors**, which are the smallest units which the hard drive can read or write. These can range from 512B to today's 4096B. There are two main ways to address a sector:
- **Cylinder-Head-Sector (CHS)** addressing uses the coordinates of the specific cylinder, the head that should read it and the sector on the cylinder that should be read. This is useful for smaller disks with a small amount of sectors. This kind of addressing takes places in the OS.
- **Logical Block Addressing (LBA)** uses a linear logical numbering for the sectors from 1 to N. It is used commonly in modern times as it simplifies the process and the search of the specific sector is done in the hard drive and not in the OS.
#### Terms
- **Disk Sector** is the smallest unit space the disk can read or write.
- **Allocation Block** is the smallest unit of space the OS will work with. This is usually 2<sup>N</sup> sectors.
- **Fragmentation** means that the data is saved non continuously in chunks. This slows down operations with the disk. It is possible to defragment a disk by reordering stored data so they are continuous.
	- **Internal** fragmentation means that there are fragments inside of allocation blocks. The file system allocates more room a file then is its true size.
	- **External** fragmentation happens between allocation blocks. This means that a file that is saved over several allocation blocks is saved in segments that are not continuous, with other allocation blocks in between them. This happens due to deletion of files which frees up the allocation blocks, but which is smaller then the file in need of saving, which means that it has to be spread around into these empty places. This can also happen if a file grows in size past the size of the allocation block, but in there is already something stored in the next block and so the next part of the file has to be stored elsewhere.
- **Access to Disk** (reading, writing) must be planned ahead in relation to the current position of the head. Each request for access can be ordered in a way that the head can move between each of them with the least amount of movement as possible. There are approaches to this such as moving the head from the center to the edge and back in a loop and so on. Completion of operations is announced with [[Interrupt]]s.
- **Logical Disk** is division of a physical disk into disk **partitions**, with which we can work independently. Table MBR (**Master Boot Record**) or more new GPT (**GUID Partition Table**) contains information about these partitions.
- **Journaling** uses the same idea as DB journaling, which to keep the data consistent during a write operation. Operations are written into a journal and then once completed they are erased. If a fault appears then by using one of two methods **REDO** or **UNDO** we can either try to write the data again or undo it.
- **Copy-on-Write** uses a principal of keeping the old while writing the new. Initially when writing the new data is written into new blocks inside the tree and once all of them have been writing down the system rewrites the master block from the old block tree address into the new one. This means that even if a fault appears then the old data is still safely stored and available, until the last operation of the write that only practically changes the pointer.
#### Typical parameters
- Disk space up to 20TB
- Time to access data is usually in low **ms**.
- Transfer speeds are usually in the range of **tens to hundreds of MB/s**.
#### Redundant Array of Independent Disk (RAID)
A method by which the data on the disks can be protected against disk failure. Comes in several levels, each one increasing in level os safety:
- **Raid 0** also called disk stripping means that each block of data is stored on a separate disk which greatly increases throughput, but does nothing for safety.
- **Raid 1** also known as disk mirroring uses two drives to store the same data, pretty much meaning that if one fails we still have a perfect copy. This has high redundancy, but has the through put of only one disk.
- **Raid 2** in which data is stored by bites across disks and secured by [[Hamming Code]]. Has lower redundancy then RAID 1, but through put is better.
- **RAID 3-5** use [[Parity]] to protect from one disk failing.
- **RAID 6** uses two [[Parity]] blocks unlike RAID 5, which means it can recover from 2 disks failing.
### Solid State Drive (SSD)
Solid state drives use a different technology from HDDs. They use arrays of non-volatile [[Flip-Flop]]s arranged into grids layered over each other. These blocks and layers are organized into what are called **pages**, where each page can have the size from 4096B to 4KB and these pages are commonly arranged into **blocks** that have typical size of 128 pages (so in total 512KB of storage). When working with SSDs we have to remember that:
- Empty pages can be written into by themselves.
- For rewriting a pages we need to load the entire block into [[Cache (RVP)]], make the necessary changes and then delete the original block from the SSD and write down a new one. 
- This can be solved by a SSD controller that can move around and free pages and blocks without the need to load them. 
- SSD can also have pages above the described capacity for writing down and then moving around blocks.
## UNIX File System
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
## Other Types of File Organization
Organization and description of files should be implemented in a way that it should **minimalize overhead** while working with it and it should be **simple** to:
- **Go through a File**, which is tied to way of finding the next block.
- **Moving of Files** which is tied with the way of finding the first and a specific file block.
- **Expanding and Contracting a File** which is tied to adding and removing of blocks.
### Continual Storage
Simple data is stored in a disk sequential order (one after another). Problem is **expanding of files** and **external fragmentation**.
### Linked Block List
Each block contains not only data, but also a **link to the next block** or the end of file symbol. An issue with this is **random access** to block as it always is read sequentially. Any issue with the links can also cause the loss of the file. Solves the issue of external fragmentation.
### File Allocation Table (FAT)
Similar princip to linked block list, but instead of the links being stored at the end of the block they are stored in a table. This table it called a file allocation table, which is saved at the beginning of a disk (twice for redundancy reasons). Each cell in the table contains a link to the data block on the disk. This partially solves the issue with random access, but the going through the FAT is still sequential.
### B+ Trees
Today these trees are the most commonly used way of storing files on a disk (can include modifications). It solves the **issue of sequential and random access** to the data. The effectivity of B+ trees is based on its time complexity of [[Time and Space Complexity|O(n * log n)]] when searching through the tree.
#### Tree Structure
- **Internal Node** is made up of **K** amount of keys (identification of blocks, their sequential number) and **K + 1** links to nodes of lower level. The keys in a node are **ordered sequentially** (from lowest to highest) and the keys next to each other define the interval of keys between them. These interval are **closed from the left** and **open from the right** meaning that on an interval key **i** to key **i+n** if we are looking for key **i** then it is in this interval. Because the keys are ordered the searching can also be done through **halving of the interval**.
- **External Node** (or leave nodes) have the same structure as the **internal nodes**, but instead of pointing to another level of the tree **they point at the data blocks**. The last link in this block also link to the next external (leave) node in sequence, which makes it easy to continue on sequentially reading the data blocks if needed. The values of the data block keys can be affected by fragmentation, which requires all of the keys to be written down, otherwise it might cause issues.
#### Properties
- **B+ Trees** are height balanced and it applies to them that:
	- **Fullness Limit** for a node with **m** links (so keys from 1 to m-1):
		- Sole root from 1 to m-1
		- Root from 2 to m
		- Internal node from m/2 to m
		- External node from m/2-1 to m-1
	- **Insertion** is done on the **leave level** and if the node overflows then the node splits and can even split higher level nodes up until the root is split. In case the root split the entire tree grows in level.
	- **Deletion** is also done on the **leave level** and if the minimal rule for fullness is violated then the tree either consolidates the remaining entries into other nodes or it unification of two node into one that does not violate the fullness rule. This can also lead to unification of higher nodes up until a new root is formed through unification, in which case the tree goes down a level.
### Extents
Extents link to a **dynamic amount of blocks** that are **logically** in a row (are sequential) and **physically** in a row (are sequential). This speeds up work with large files and lower the amount of metadata. Extents can be combined with **B+ trees**, but they cannot be used in a Unix tree, because there is no way to store the information about their dynamic length.
### Extent Trees
Similar to **B+ trees**, but without the need to balancing and sequential last level. It is restricted to a maximum of 5 level. Its root is stored in an **i-node** and has 4 links (which is enough for small files). Internal nodes can have more then 4 links. The internal node is created when the root is filled, all of the root's links are transferred over into it and the link to the internal node is place in the root. Internal nodes have a **header** in which they keep the number of current links, the maximum amount of links and doubles containing the number of the logic block and the number of the physical block (this can point to either the data or another internal node).
### New Technology File System (NTFS)
A file system developed for Windows NT. It uses a **Master File Table (MFT)** in which it keeps a row for each file. The contents of the file then can be addressed through:
- **Directly** from the MFT
- linked from the MFT using **extents**
- linked from the MTF using a **B+ tree**, which is made up of other MTF entries which are linked to from the primary MTF entry
## Organization of Free Space
Free space can be organized and addressed through:
- A **bit array map** that with one bit per one block, which can be searched through with bit masking
- A **linking** of free blocks
- A **linking of link in a FAT**, that link to free blocks
- A **B+ tree** which can address through size or offset
- By **extents**
## Deduplication
**Restriction of repeated storing** of same data on either the file, extent, block byte level. This can save space for example on email servers that can receive one mail for hundreds of recipients, git repositories and so on. This can be implemented in **writing** or **additionally**, and uses cryptographic hashing for searching for a match. A problem arises once one of the shared files is updates, which requires for the file to be duplicated and one of the updated. With small duplication this can increased CPU, time or space consumption.
## Adding Disks
A new disk and other devices can be added to any directory of an already existing file system. Today most of all [[Operating Systems]] automatically mounts disks after connecting them to the PC.
### Virtual File System (VFS)
Creates a unified interface for work with different file systems. This separates the higher level of an [[Operating Systems]] from the specific implantation of individual file system operations in individual file systems.
### Network File System (NFS)
Makes available files stored on different systems. This is connected/integrated into **VFS** and working with it for the [[Operating Systems]] and the user is identical to working with files on a disk.
### Spooling
Is the simultaneous peripheral operations on-line. It allows to speed up of slow output devices such as when printing through a printer. The outcome is done into a file and a process, that started the operation can continue. The created file is saved into a queue of requests to the output device (printer) and waits for its turn.