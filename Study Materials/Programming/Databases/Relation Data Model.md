Relation databases are based upon definition of sets, Cartesian multiplication and relations, as they are known from math. Relations are a subset of a Cartesian multiplication and in case of relation databases we understand them as tables. A specific table is made out a **scheme of relations** (table header, names of the columns) and a **relation body** (represent stored data in a table in rows). We can say that the amount of attributes in a relation is a level (order) of the relation, cardinality of the body (number of rows) we can signify as a cardinality of the relation. The fact we use **relation model** and **relation databases** is derived from the fact that relation is the basic abstracted term of the model and the only structure of a database on a logical level.
## Model Terms
- **Domain** is a set of scalar values of the same type that an atribute can become.
- **Scalar Value** is the smallest sematic unit of data, it is atomic, there is not structure in it.
- **Composed Domain** is a domain composed only of simple domains.
- **Relation Attribute** is the column of a table. It is in essence description of the values.
- **Relation Tuple** is a row in the table.
## Relation Database Scheme
Database scheme for a relation database is a **double (R, I)**, where:
- **R = {R<sub>1</sub>, R<sub>2</sub>,... , R<sub>n</sub>}** - is a set of relation schemes.
- **I = {I<sub>1</sub>, I<sub>2</sub>,... , I<sub>n</sub>}** - is a set of integrity restrictions.
## Integrity Restrictions
Rules that restrict the stored data in a database that are derived from reality.
- **Specific** for a specific application (value cannot be NULL, only certain values can be added, etc.)
- **General** that are true in every database (primary keys, foreign keys, etc...)
### Candidate Key
An attribute or composed attribute for which applies:
- Is **unambiguous**.
- Is **minimal** (cannot be reduced)
### Primary Key
Primary key is one of the candidate keys. It is used as the basic source for addressing relation tuples in the relation model. No component of a primary key can be an empty value (NULL).
### Foreign Key
Attribute or a composed attribute of relation R2, for which applies:
- All of its values are set or they are all empty.
- In a Foreign key is a value that is identical with some value of a primary key in another relation R1.
## Relation Algebra
Relation Algebra is a double **RA = (R, O)**, where:
- **R** is a set of relations
- **O** is a set of operation with the relations
The set of operations consists of:
- **Basic operations with sets** such as unification, conjunction, difference, Cartesian multiplication.
- **Special operations with relations** such as projection, joining, division.
Traditional set operations have the same outcome as with normal sets, but can be done with relations, that have the scheme with the exception of Cartesian multiplication.
### Projection
Projection is an operation in which we choose only some columns from the original table. From relation **R** we create a relation `R[X,Y, ..., Z]` with a scheme `(X, Y, ..., Z)` and a body that contains the reduced tuples that are conformed with the new scheme. This is for example done in [[Structured Query Language (SQL)]] with the command **SELECT** like `SELECT name FROM users;` Part of this operation is also reduction of duplicit entries (tuples), that are created with the projection (SELECT does not do this).
### Selection (Restriction)
Restriction is an operation that keeps the original scheme of the relation, but select only entries (tuples) of that relation that meet some kind of a condition. In [[Structured Query Language (SQL)]] this is done through the **WHERE** command like `WHERE id = 42`.
### Join
Join is an operation that combines two relation schemes, in a way the final relation scheme will contain all attributes of the original relation and at least one of the attributes of the original relations will be share. By this shared attribute is the join operation done in a way that tuples of original relations that have the the same value are put together. In [[Structured Query Language (SQL)]] it is done through:
- **INNER JOIN** (companies **ON** names.id = companies.id...) returns entries from left table that have a corresponding entries in the right table.
- **OUTER JOIN** (companies **ON** names.id = companies.id...) return all entries if the have connections or not, with entries that do not have connected entries their attributes will be left empty.
- **LEFT JOIN** (companies **ON** names.id = companies.id...) return all entries from the left table with attached entries from the right table, but only those that have connected entries in the left table.
- **RIGHT JOIN** (companies **ON** names.id = companies.id...) return all entries from the right table with attached entries from the left table, but only those that have connected entries in the right table.