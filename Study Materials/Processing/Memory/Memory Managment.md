We differentiate between:
- **Logical Address Space (LAP)** which is virtual address space, with which the [[Processor]] works while working with code. Each process and core has its own and they are identical (multiple logical addresses can be mapped to different physical addresses). A slice of virtual memory with a fixed size we call we call a **page**.
- **Physical Address Space (FAP)** is only one for the entire computer and is shared amongst all processes and cores. It is the physical address space of the **operational memory**. A slice of physical memory with a fixed size we call a **frame**.
## Memory Managment Unit (MMU)
It is a [[Hardware (HW)]] component that makes sure the logic addresses are translated into physical addresses. It is commonly part of the chip. To translate the addresses MMU uses special registers and the operational memory. To speed this up it also uses various buffers like a **Translation Lookaside Buffer (TLB)**.
### Translation Look-aside Buffer (TLB)
It is a quick associative buffer, that allows for paralel (or partially parallel) search based on the page number for the frame number. **TLB** contains selected entries from page tables and does not contain data of the pages/frames. Selections of stored entries in the **TLB** is key for quick access to the memory. We differentiate between **TLB Hit** and a **TLB Miss** which corresponds to the if the buffer had the necessary page numbers or did not and it needs to be loaded. In theory on an access the a random part of the memory the chance of hitting is quite slim, but in practice the chance to hit is much higher around **98%** to **99%** due to spatial and time locality of memory. Processors pre-emptively load expected mappings into the TLB. An instruction can still technically experience **4x** TLB misses, instruction is in two pages and operands are also in two pages and neither is in the TLB. **TLB Miss** can be solved through:
- [[Hardware (HW)]] automatically searches in the page table, which is more expensive but quicker.
- Some control is handed over to [[Software (SW)]], which inputs into TLB the required double and the search in the TLB is repeated. 
When **changing the context** it is necessary to also **change the entries in the TLB**. This can be done by signing of some pages as global ones or by adding process identifications into the TLB, which means that the entries do not have to be exchanged. The TLB entries also have to be removed if the mapping is changed.
## Allocation of Memory
To map **FAP** in the **LAP** the size of one segment (block) of the memory is used, which is consistent with the translation of **LAP** to **FAP**, meaning it is supported by the hardware. The segments are:
- **Sequential Blocks**
- **Segments**
- **Pages**
- Combined approach
While programming (for example in C malloc) we are getting already mapped segments of the **LAP**.
### Contiguous Allocation
Memory is allocated to processes in **continuous blocks** of memory of a certain size. If there is not currently a chain of blocks big enough for the process then it has to wait or the memory of an entire other process must be placed onto the disk.
- **Pros**: it is very easy to implement in [[Hardware (HW)]] and [[Software (SW)]].
- **Cons**: it suffers from **external fragmentation**. Another issue is increasing the size of the current space. There are some strategies to mitigate this, but that complicates the implementation.
### Segmented Allocation
**LAP** is divided into several segments. These segments are allocated for different aspects of the process such as heap, stack, etc. by the compilator or the programmer. Each segment has a specified mode of access. **Logical address** is made up of **segment numbers** and **offsets** in them.
- **Pros**: easy implementation, improves the issue with external fragmentation, but the problem with dynamic segment sizes remains.
- **Cons**: Segmenting of the program is decided upon its creation or compilation, which can have problems during implementation. It still does not fix the problem with external fragmentation.
### Page Allocation
**LAP** is divided into **pages** of **fixed size** which usually corresponds to the size of one block on the disk. **FAP** is divided into **frames** of the same size as **pages**. We always map one page to one frame and mapping is obscured from the implementation of the program. To increase effectivity the access to memory is usually mapped into sequential chains of frames, but that does not have to be guarantied.
- **Pros**: eliminates external fragmentation and obscures the physical memory allocation from the process. Allows for **soft setting aside** of pages/frames, which means that the process does not have to be slowed down, but parts its not using can be set aside.
- **Cons**: More complicated implementation both in [[Hardware (HW)]] and [[Software (SW)]] and requires more resources for upkeep. Paging also causes **internal fragmentation**.
### One-Level Page Table Allocation
**Easiest** but practically **unusable** way of implementing page tables. [[Operating Systems]] keeps information about free frames and if a process including cores keeps its own **page table**. The address to this table is stored in a **register**. The page table contains description of mappings (logical address of the page and the first address of the frame) and several signs such as dirty bit. Tables same as data are stored in the Operational Memory, which is the root of the usability of this method.
	One a 32-bit system there exists 2<sup>32</sup> addresses. A page has only 4096B, which is 2<sup>12</sup>B and it is necessary to keep information about 2<sup>20</sup> pages. One entry in the table can have 4 bytes, which means 4MB to store pages for one process. This problem grows exponentially on 64-bit systems.
When executing a command in a program there happens to be two access into the memory, one for the instruction and for its operands. This leads to two access to the page table. This can be speed up using **TLB**.
### Hierarchical Page Table Allocation
Eliminates the issues with **excessive size of the page table** and on modern processors there are page tables with 4 levels. These tables are kept in a tree and in the memory are only kept the once that are necessary. The information about the **pages with data** are usually on the **leave level**, but can also be kept in higher levels, in which case the frame has a bigger size such as 2MB or 1GB. With hierarchical page tables increases the reason to use **TLB** as in case of a miss it is necessary to go through the hierarchical structure. This can be improved for example by having different TLBs for code and data.
### Hash Table Allocation
This princip uses hash tables with explicit synonym chaining using a list. The length of the list can be restricted, in which case a miss would be handled by [[Software (SW)]]. Each process can have their own hash table or there can be one hash table shared amongst them all, in which case they need further signing.
### Inverted Page Table Allocation
For each frame it describes which process has which page mapped to it. Index into this table corresponds to the frame number. To speed up searching hashing functions can be used. A problem is sharing memory across processes.
## Paging and Segmentation on Request
It is impossible, for the entire **LAP** of one process or multiple processes, to be mapped into memory. The process does not know that its **LAP** is not mapped into the physical memory. **Pages** are mapped to **frames** and thus allocated into RAM only when they are needed. To map a page to a frame is time intensive operation, which is a reason why we are trying to eliminate this, processor thus pre-emptively loads pages into memory before the process needs them. When all frames are in use it is necessary put some of them aside onto the disk into what is called the **swap area**, which usually leads to system slowdown. Information about loaded and swapped pages is tracked by the core in its own structures (memory), MMU does not have information about them. When a page is missing, which happens when a process points to a page that is not loaded in a page table (or other structure) the MMU generates an [[Interrupt|Interruption]]. The core must solve the missing page.
### Steps to Solving a Missing Page
1. Check if the process is not pointing outside its dedicated space.
2. **Allocation of a frame** which is either empty or a sacrifice must be chosen. If the chosen frame was modified signified by a **dirty bit** then it has to be put into the **swap**.
3. **Page Initialization** means that any data in the previous page must be **devaluated** so the process that gets the page cannot abuse it.
4. Updates the page table to reflect the changes.
5. Process can then repeat the instruction.
Several missing pages can happen while executing one instruction (code of the instruction is in different pages, operands are in different pages, etc.). The top level page table must be protected from a missing page.
## Sacrifice Selection Algorithms
The selection of a page to be sacrificed can be either:
- **Global** which means that any frame of any process can be used
- **Local** only a frames of the process that has a missing page
Typically there is a process called **page deamon** that is executed once there is not enough pages and frees a specific amount of frames. During a missing page a free frame is used. Additionally if the process from which the page was sacrificed requires the page in its next steps then that page is returned to it and another sacrifice must be chosen. When choosing a sacrifice the unmodified pages are **prioritized** as they do not require getting put into the **swap**. Process always has to have a minimum amount of frames to execute one instruction, otherwise it must be paused. The number of frames a process is allocated is based on some heuristic (priority, size of the program, number of interruptions).
### First In First Out (FIFO)
Chooses the page that was allocated first (was in the memory the longest).
- **Pros**: Easy Implementation
- **Cons**: Can remove important pages that are still in use.
### Least Recently Used (LRU)
Chooses the page that was used the least (the process did not use it the longest time out of all). This is a good approximation of the best page to sacrifice, but requires [[Hardware (HW)]] support as there is need to keep time stamps about when each page was used or some other approach that can approximate it. One of doing that is to use several bits as timestamps, setting the [[MSB]] to one when used and then the system periodically shifts these bits aside until all of them are zero or are refreshed.  The sacrifice is then the page with the lowest number.
- **Pros**: Is quite good at selecting the right sacrifice and not causing other missing pages.
- **Cons**: Requires [[Hardware (HW)]] support and does not work for cyclical walks through arrays.
## Trashing
It is a problem that happens when there is a high strain on RAM  and not enough frames. Solving the missing frames then takes longer then the actual calculation. One way to solve this is to completely pause some of the processes and moving their data onto the swap and then returning them back once the issue was solved.
## Shared Pages
It is used for common libraries such as **.dll** and **.so**. In the **FAP** are libraries loaded only once and multiple processes can access them as they are mapped several times into the **LAP**. Shared pages also allow for **Inter Process Communication (IPC)** where two processes can use the same segment of **FAP**.
## Memory Mapped Files
Blocks of files from the disk are mapped into onto pages in the memory and can be accessed through normal access reading and writing into memory. This allows for shared access to files.