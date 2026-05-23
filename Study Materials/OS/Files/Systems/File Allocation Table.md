---
tags:
  - IOS
aliases:
  - FAT
  - FAT32
sources:
---
Similar principal to [[Linked Block List]], but instead of the links being stored at the end of the block they are stored in a table. This table it called a file allocation table, which is saved at the beginning of a disk (twice for redundancy reasons). Each cell in the table contains a link to the data block on the disk. This partially solves the issue with random access, but the going through the FAT is still sequential.