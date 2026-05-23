---
tags:
  - IOS
aliases:
  - extend
sources:
---
Extents link to a **dynamic amount of blocks** that are **logically** in a row (are sequential) and **physically** in a row (are sequential). This speeds up work with large files and lower the amount of metadata. Extents can be combined with [[B+ Tree]], but they cannot be used in a [[UNIX]] tree, because there is no way to store the information about their dynamic length.