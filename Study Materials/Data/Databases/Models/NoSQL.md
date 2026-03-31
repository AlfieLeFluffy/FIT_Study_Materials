---
tags:
  - UPA
  - to_be_finished
aliases:
  - Not only SQL
  - noSQL
---
In response to [[Modern Database Trends|modern database trends]] NoSQL was developed.
## Properties
Some basic properties of NoSQL databases:
- Support non-relational data models such as:
	- **Key-value**
	- **Document**
	- **Graf**
- Supports distributed architecture. Can be used as both centralized or distributed.
- Most NoSQL databases are open-source.
- Most often solve [[Consistency Availability Partition Tolerance]] by restricting data consistency through [[Basically Available Soft-state Eventually consistent]].
### Key-Value
One key only corelates to one value and there can be no duplicates. 
- A key can be comprised of several parts, for example main and specifying, which can be use as an ID of structure and element. 
- Access to the database is handled through hash tables, which extremely quick. 
- The stored value is a BLOB and the database is not trying to understand it. 
- The value processing is done on an application level, the database only stores it in one piece.
- If we only need parts of the value or want to write only to a part of the value it is not very effective. Can be solved by extracting part of the value into a sub-element with its own key.
Examples of such databases are Oracle NoSQL and Dynamo.
### Document
Basically the same as key-value, but the value is structured.
- The database sees into the value and can understand it and analyse it.
- Values can be stored in formats such as XML/JSON or even as an object.
- Values can refer to other entries, can contain nested structures, collections, etc.
Examples of such databases is mongoDB.
### Column
Rows are similar to [[Relation Data Model]].
- Rows are a collections of key-value, where the key is the name of the column.
- Columns can be different for each row.
- Can contain supercolumns, where each row contains a collection of superculumns in which each one contains a collection of columns.
- The database is thinner, multidimensional and uses an ordered mapping functions.
Examples of such databases are Cassandra and BigTable.
### Graph
Databases that model [[Graph|graphs]] with objects as vertexes and their relations with edges.
- Differing implementations of storage.
- Used for representation of networks and topologies.
- [[RDF]] databases use a specific category of graph NoSQL databases.
Examples of such databases are Neo4j and AllegroGraph ([[Resource Description Framework|RDF]]).
## Relation vs NoSQL
NoSQL databases are modern and favoured in cloud storages, but it is appropriate to use to only for specific cases. For classic information systems it is still better to use relational databases. When choosing a NoSQL database it is important to take into account:
- Type of storage and data organization.
- Properties of distributed architecture.
- Scalability options.
- Options of application integration.
## Quering
NoSQL databases are mostly distributed key-value databases. The key is utilized to find both the correct data node storing the key-value pair in a cluster and the local disk block where the value is stored for the key.
## Partitioning and Sharding
NoSQL usually implies performance, scalability, fault tolerance and more for which to accomplish NoSQL databases partition data horizontally. This means that the data is split up into groups by a shard key and stored in separate shards. There are various ways of doing horizontal partitioning (strategies) such as by range of values, by hash, by access frequency, by insert time, etc. Most common of these strategies is by hash of the key.  