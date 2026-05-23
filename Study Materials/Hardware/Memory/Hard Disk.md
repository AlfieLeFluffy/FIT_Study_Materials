---
tags:
  - IOS
aliases:
  - hard disk
  - Hard Drive
  - hard drive
  - HD
---
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