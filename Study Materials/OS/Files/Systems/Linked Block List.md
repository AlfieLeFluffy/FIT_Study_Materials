---
tags:
  - IOS
aliases:
  - linked block list
sources:
---
Each block contains not only data, but also a **link to the next block** or the end of file symbol. An issue with this is **random access** to block as it always is read sequentially. Any issue with the links can also cause the loss of the file. Solves the issue of external fragmentation.