Quick buffering memory close to the processor (RVP, rychlý vyrovnávací paměť) that helps to achieve the quickest load/store times then what could be achieved only by using [[OS]] memory (RAM).
## Properties
- In processors it is usually divided into several layers, such as L1 and L2 for each core and L3 shared between cores. 
- This hierarchical division of memory tries to eliminate the differences between [[CPU]] speed and the speed of the [[OS]] memory.
- Cache is divided into blocks of constant size that should ideally be identical to the size of [[OS]] memory [[Frame]]s.
- [[OS]] memory usually have much more blocks of data then cache does.
- There are mechanisms that select which [[Frame]]s should be loaded into cache.
- These mechanisms should work with a rate of success, otherwise the system would need to spend a lot of time loading missing data.
- Some of the properties of mechanisms and cache are:
	- **Hit Rate** is the chance that the data the systems seeks is in the cache. Usually should be around 95-99%.
	- **Miss Rate** inverse of hit rate (1 - Hit Rate).
	- **Access time** is the time to get access to data that are stored in cache.
	- **Loss time** is the time to get access to data that are not stored in cache and have to be loaded.

## Organization
The way the cache is organized is based upon the way the elements are mapped from the [[OS]] memory to the cache. Its main purpose should be to reduce **Miss Rate**.
### Direct Mapping
Elements are mapped into the cache based on their addresses in OS memory, but as the cache is a much smaller space and address space, the top order bits masked over (only some lower portion of the address is used **12|3456** -> **3456**). This can create an issue where if multiple blocks of OS memory with the same lower addresses need to be loaded in at the same time it creates and issue that they cannot exist in cache at the same time.
With random access for a cache with 2<sup>10</sup> blocks and main memory of 2<sup>30</sup> frames, the probability of a hit would be 2<sup>10</sup>/2<sup>30</sup> or 0.0001%. In practice due to [[Memory#Locality Principal|Locality Principal]] this number is closer to 90% as the access is not completely random.
### Multi-Path Mapping
Allows to map blocks with the same lower addresses. This is done by splitting the cache address space into several tables (2,4,...). With each entry in these tables also has to be stored the upper part of the address, so that the correct entry could be chosen to write/read. To create a muli-path cache of the same size as a direct cache it requires a greater overall capacity and a logic (comparator) that chooses the right cache entry that should be worked with.
### Full-Associative Mapping
Is created by increasing the degree to which the entries in the table are associated with their main memory entries. This can be done to such a degree that the cache addresses are no longer relevant and any cache entry can be stored in any cache block. This requires a significantly sophisticated and powerful way of comparing the cache entries to locate the required block that needs to be done in paralel. In practice this is not used as it is too complicated and expensive. 
### Pros/Cons to Mappings
There are two main ways to increase cache Hit Rates:
- Increase the cache capacity and with the also the cache address space.
- Decrease the size of each block.
With multi-path mappings there also needs to be a way to choose a sacrifice if all possible entries for a single lower address are full. This can be done through methods such as [[LRU]], [[MRU]], [[FIFO]], etc...

## Data Consistency
When it comes to writing data into cache entries closest to the [[CPU]] it is necessary to invalidate all other lower cache entries and main memory entries to avoid from errors created by working with old data before they had the chance to get written over. This issues is important especially for multi-core processors that each have their own high cache levels (L1,L2). In this case the processor needs to invalidate data from one core's L1 cache to all other L1 caches in other cores so they are forced to reload the now new values.
There are several methods that provide this consistency guarantee:
- **Write-Through** (direct writing) - When a cache entry is change it is also immediately changed in the main memory. It is an easy solution to implement, but can run into issues such as if the entry is rewritten too often then the main memory can become a bottleneck. This approach can be further divided into:
	- **Write-Through with Write Allocate** - If the written data are not in the cache then they get loaded.
	- **Write-Through with no Write Allocate** - The written data are not loaded into cache.
- **Write-Back** (backwards writing) - To modify an entry to a lower level of memory (main) only happens when the entry is deleted (push out) of the cache. This is a quite inefficient way as this approach rewrites the data every time and not just when the entry was modified. To solve this the entries are signified with a change flag (dirty bit) and the writing then happens in one of two ways:
	- **Flagged Write Back** - The writing to main memory only for those entries that have been modified, have the dirty bit.
	- **Flagged Register Write Back** - Same as before, but instead of being directly written into main memory they are first written into a help buffer that allows others to read it before it gets stored in main memory, increasing throughput.
- **Write-Buffer** (writing into caches) - Expands the Write-Back approach in a way that when a sacrifice entry is chosen, instead of immediately storing it back into main memory, the entry gets stored in a buffer where it waits until all read operations for the main memory are resolved.