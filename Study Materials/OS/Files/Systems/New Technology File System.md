---
tags:
  - IOS
aliases:
  - new technology file system
  - NTFS
sources:
---
A file system developed for Windows NT. It uses a **Master File Table (MFT)** in which it keeps a row for each file. The contents of the file then can be addressed through:
- **Directly** from the MFT
- linked from the MFT using [[Extend]]
- linked from the MTF using a [[B+ Tree]], which is made up of other MTF entries which are linked to from the primary MTF entry