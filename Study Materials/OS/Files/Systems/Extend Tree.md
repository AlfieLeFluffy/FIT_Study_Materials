---
tags:
  - IOS
aliases:
  - extend tree
sources:
---
Similar to [[B+ Tree]], but without the need to balancing and sequential last level. It is restricted to a maximum of 5 level. Its root is stored in an **i-node** and has 4 links (which is enough for small files). Internal nodes can have more then 4 links. The internal node is created when the root is filled, all of the root's links are transferred over into it and the link to the internal node is place in the root. Internal nodes have a **header** in which they keep the number of current links, the maximum amount of links and doubles containing the number of the logic block and the number of the physical block (this can point to either the data or another internal node).