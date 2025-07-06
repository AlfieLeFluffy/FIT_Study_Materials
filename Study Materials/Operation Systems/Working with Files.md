To speed up work with files buffers ([[Cache (RVP)]]) are commonly used, that minimalize operations with slow peripherals such as [[File Systems#Storage Types| HDDs, SSDs]] or terminals. Partial caches have the size of one data block or a group and are grouped into collection of either static or dynamic length. A possible implementation of these are through [[Searching|Hash Tables]].
Between a process and the data on a disk there is a [[Kernel]] and buffers. To get to these buffers a has table is used, where a the entries in the table point towards the buffer blocks.
## Operations with Files
### Reading
The procedure to read a file for the first time (is not in a buffer) is:
1. Allocation of a buffer and loading (reading) of blocks (either the first or the asked for).
2. Copying of desired data from the buffer into the address space of the process (RAM -> RAM).
If the data are already in the RAM then only the second point is done. If the reading steps over into another data block then all the steps are repeated.
#### read()
1. Checks validity of **fd** (file descriptor).
2. Goes through steps 1. and 2. described above as necessary.
3. The return value is the number of truly read bits or a **-1** if an error occurs and an errno is set.
### Writing
The procedure to write into a file is this:
1. Allocation of a buffer and loading of data block into the buffer (if the file is new or the file is overwritten and not updated then this is skipped). 
2. Writing of data into the buffer from the address space of the process (RAM -> RAM) and setting of the **dirty bit**.
3. **Delayed** writing to the disk, which nulls the **dirty bit**.
#### write()
1. Checks validity of **fd** (file descriptor).
2. Goes through steps 1. and 2. described above as necessary.
3. Before the writing it checks if there is enough space for the file on the disk.
4. The return value is the number of truly written bit into the file or a **-1** if an error occurs and an errno is set.
### Opening
At first (during the step 1) the system checks for access rights.
A file **not yet open**:
1. Search for the **i-node** of the file based on the **filename** and the names of the **directories**. Directories are sequentially opened until the i-node of the file is found. Some i-nodes can already be in the buffer.
2. In the **system table of active i-nodes** is allocated a new entry into which the **i-node** is loaded and become the **v-node**, which is its expanded copy.
3. In the **system table of open files** is allocated a new entry and gets filled with:
	1. Link to the **v-node**
	2. **Open Mode**
	3. **Position in the File** (0)
	4. A **counter of number of references** to this entry. This number grows and decreases with the number of **file descriptors**.
4. In the **array of file descriptors** (each process has its own) is allocated an entry for the new file descriptor and gets filled with a link to the **open file entry**.
5. The link to the **file descriptor** is returned.
A file **was already open**:
ㅤ
1. **Look up of the i-node number**#
2. **Look up of the v-node** in the system table.
3. Allocation of a new entry in the **system table of open files** (is only shared during a fork), filling it with the **v-node** and incrementing the number in the v-node.
4. Creation of a new **file descriptor**.
5. Returns the **file descriptor**.
### Direct Access
Is done through command `lseek`:
1. Checks of **file descriptor**.
2. Sets position of **file descriptor to byte offset**.
3. Returns value of the **final position** or **-1** when error appears.
While using seek after the end of the file and writing there it creates what is called a **shallow file** (the file has empty space that is not saved on the disk). The offset can be negative, but cannot get past the beginning of the file.
### Closing
Closing a file **does not** cause it to be stored **from the buffer to the disk**. The steps are
1. Checks of **file descriptor**.
2. Frees the **file descriptor** and decreases the number in the **open files table**.
3. If the number of references decreases to a zero then the **open file table** entry is **freed** and decreases the number in the **v-node**.
4. If the number of reference in the **v-node** decreases to zero then it copies the **i-node** information into the buffer and then the **v-node** is freed. 
5. Return **0** if successful or **-1** if it fails.
### Deleting
To delete a file the steps are:
1. **Resolves the filepath**, checks for existence of the file and checks for access rights.
2. **Removes the static link to the i-node** in the directory.
3. Decreases the number of links to the i-node.
4. If the number decreases to 0, the i-node and all of its data can be freed. This happens after all process are done working with the file. This means that on UNIX the file can be deleted even if a process is using it, unlike in Windows.