---
tags:
  - IDS
  - UPA
aliases:
  - acid
---
## ACID
Acronym for properties transaction apply:
- **Atomicity** all of the operations are done or none are done. No command should be done if not all are done, essentially turning them all into one atomic operation.
- **Consistency** means that the transaction will keep the database consistent, that it will not break any of the [[Relation Data Model#Integrity Restrictions|Integrity Restrictions]].
- **Isolation** means that none of the unfinished operations in a transaction will affect other ongoing operations until the transaction is committed. 
- **Durability** means that once a transaction is committed then the changes it makes have a permanent character, meaning that even if the power goes out the changes remain.