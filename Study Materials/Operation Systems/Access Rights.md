Access right to files and other such objects are done for security reasons. There are different access right for the **owner**, a **group** and **others**. 
## Format
A common format for access right is through a bit array in which each bit corresponds to:

| Normal files |                 |
| ------------ | --------------- |
| r            | read file       |
| w            | write into file |
| x            | execute file    |
| Directory    |                 |
| r            | read contents   |
| w            | update contents |
| x            | access contents |
The format is then 1 reserved bit and 3 bits for each **owner**, **group** and **others** in order. These bits can also be converted into their decadic values for shorter notation. An example can be:
```
-rwx---r--
0704
```
### Sticky Bit
Sticky bit or **t** is a sigh that disallows cancelation and renaming of foreign (not owned) files in an directory, even though everyone has the right to read and write. This bit is added at the end as:
```
-rwxrwxrwxt
```
### Process Access Rights
For processes we have:
- **UID** which is ID of the user that executed it.
- **EUID** which is effective **UID** for control of access rights.
- **GID** which is ID of a group of which the user is a part of.
- **EGID** which is effective **GID** for control of access rights.
- **SUID/SGUID** which is for lending right to users.