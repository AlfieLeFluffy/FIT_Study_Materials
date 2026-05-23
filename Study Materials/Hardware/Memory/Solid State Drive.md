---
tags:
  - IOS
aliases:
  - solid state drive
  - SSD
---
Solid state drives use a different technology from HDDs. They use arrays of non-volatile [[Flip-Flop]]s arranged into grids layered over each other. These blocks and layers are organized into what are called **pages**, where each page can have the size from 4096B to 4KB and these pages are commonly arranged into **blocks** that have typical size of 128 pages (so in total 512KB of storage). When working with SSDs we have to remember that:
- Empty pages can be written into by themselves.
- For rewriting a pages we need to load the entire block into [[Cache]], make the necessary changes and then delete the original block from the SSD and write down a new one. 
- This can be solved by a SSD controller that can move around and free pages and blocks without the need to load them. 
- SSD can also have pages above the described capacity for writing down and then moving around blocks.