---
tags:
  - IDS
  - UPA
aliases:
  - database transaction
  - transaction
  - transactions
---
Database structures are mechanics that allow manipulation with data in a consistent way without rollbacks in case of an issue. This means that if we want to execute several commands as part of some operation, but if we want there to be no problems if for example the operation fails, power gets cut, etc. we do not have to roll back the changes that have already been made. This is done through creating a transaction at the beginning of the sequence of commands, executing the commands (these commands are not yet implemented into the database) and finishing the transaction, which is when the commands get finalized, or dropping the transaction, which means that all of the commands are also dropped, but the databased was not yet affected by them, so no roll-backs are necessary.
## Business Transactions
As business transaction are normal day operations that users of an information system do such as creating factures, buying products, receiving shipments. These transactions are often made up of several **Database Transactions** that are meant to keep the database intact. For example each addition of an item into a facture can be its own database transaction so even if the system on the users side crashes, the data they already added into facture are already stored. We call systems that deal with these transactions [[On-Line Transaction Processing (OLTP)]] systems.