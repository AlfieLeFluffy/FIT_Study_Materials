---
tags:
  - UPA
aliases:
---
## CAP
Acronym for [[NoSQL]] databases properties:
- **Consistency**: Each node/client only see the same data at the same time. 
- **Availability**: Each request is serviced, successful or otherwise.
- **Partition Tolerance**: Functional even through network or node faults.
### Combinations
A [[NoSQL]] database can only ever accomplish to do two of the the three properties of CAP:
- **CA**: 2-phase commit with protocols to invalidate cache. Usually found in cluster databases, LDAP, xFS file system.
- **CP**: Aggressive locking and can withstand small outages. Usually found in distributed databases. 
- **AP**: Node rotation, conflict resolution, optimistic strategies. Usually found in web caching, DNS and Coda.