---
tags:
  - UPA
aliases:
  - object-relational data model
  - ORDM
---
An extension of both [[Object Data Model]] and [[Relation Data Model]] that combines the advantages of both systems and can store objects in a relation data model.
## Properties
A significant advantage of both [[Relation Data Model]] and [[Object-Relational Data Model]] is support by major vendors. Object-Relational data models expand on this with:
- Nested relational tables with object-oriented features.
- Persistent data in tables, attributes can be of ADT types, meaning both data and their operations can be encapsulated.
- Relationships can be done by [[OID|OIDs]] as well as private and foreign keys.
- In computation models the navigation can be done by both cursors and references.
- Unlike [[Object Data Model]], Object-Relationl data model was standardized in SQL-1999 and later expanded.
### Supported Features
Over the years some other features were standardizes and added into the object-relational data models, such as:
- **LOB** - Large object data types: BLOB, CLOB, etc.
- **BOOLEAN** data type.
- **ARRAY** data type.
- **MULTISET**
- **ROW**
- **SIMILAR**
- Recursive queries.
- Transaction save-points.
- Etc.
### Supported Database Engines
Some database engines that support object-relational data model are:
- Oracle Database
- IBM DB2
- Teradata Database
- Vantage Advanced SQL Engine
- Microsoft SQL Server
- PostgreSQL
## Persistence Object Storage
Applications that work with objects that require to be permanent in some way usually use some database backend that commonly works in object-relation model. 
### Properties
Persistent storage/frameworks must provide **CCSP**:
- **Continuity** means that two instances of the same object loaded into an application from the storage must be really identical, e.g., must share their state.
- **Cohesion** means a group of interconnected objects must persist together (as a cohesive group) and the application can use references to go from to another.
- **Spatio-temporal Priority** means two objects both representing one entity, existing in the same place and the same time, must be identical and have the same [[OID|OID]].
### Mapping
The storage has to somehow implement mapping of objects that can be done in one of two ways:
#### Native Mapping
Native mapping uses:
- The persistence is implemented by an object database.
- CCSP is provided by integrating the database into an application's code.
- Easy and straightforward use, but not as popular of a solution.  
#### Object-to(non-object) Mapping
Unlike native mapping:
- There is a middleware between an application and the storage backend.
- Can use both Object-relational mapping (ORM) and Obect-document mapping (ODM).
- Has some disadvantages, but is more popular.
- Some difficulties ensuring CCSP.
## Object in NoSQL Databases
An object as a data structure is identified by its [[OID]], which is a great key-value for a [[NoSQL]] database. A question is if to store the object in a [[NoSQL]] database as an object or just as a non-object data in a document form or property list.
Native object databases can be implemented as [[NoSQL]], however usually it is easier to embed the object database into an application and then use [[NoSQL]] database just as a synchronization of embedded objects database of multiple application instances. For this purposes Object-document Mapping (ODM) can be utilized with document [[NoSQL]] databases, such the quite popular MongoDB.