---
tags:
  - UPA
aliases:
  - object data model
  - ODM
  - OODBS
---
Based upon a similar principle as [[Object-Oriented Programming]]. Persistent data can be modelled and stored in objects. These objects are always unique in a database, even if they share the same values. These objects are identified through [[OID]] (object ID). An extended version of this model is [[Object-Relational Data Model]].
## Properties
Basic object data model properties are:
- Classes, attributes, operations, a unique [[OID]] which plays a significant role.
- Abstract data types (ADTs), encapsulated, polymorphic
- Attributes can be complex data-types
- [[OID]] reference relationship of objects
- Many-to-Many relationships can be direct. An attribute can contain a list of objects in relation.
- Navigation within the database is done through references or pointer to [[OID]].
During computing (working with the data) the [[OID]] plays a significant role in navigation through the references/pointer to other objects.
## Standardization
There were some attempts at standardizing the format of object oriented databases, but non were successfully. Some of these are:
- **ODMG** object model, which was only a proposal and was not accepted.
- **ODL** was not needed as the classes/objects were defined at application level.
- **OQL** was not needed as data loaded directly into application objects.