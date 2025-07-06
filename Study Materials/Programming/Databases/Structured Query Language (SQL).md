Structured query language is used to create and resolve queries for relation databases. SQL is standardized, but the implementation of each command can differ across systems and each system can have extended functionality. The language is [[Case-Insensitive]], but SQL commands are usually written with uppercase character.
## Database Objects
SQL databases use several object types such as **tables**, **view**, **index**. The are created, updated and deleted by:
- **CREATE TABLE**
```
CREATE TABLE Persons ( 
	PersonID int GENERATED AS IDENTITY PRIMARY KEY, 
	LastName varchar(255), 
	FirstName varchar(255), 
	Address varchar(255), 
	City varchar(255) 
);
```
- **CREATE INDEX**
```
CREATE (UNIQUE) INDEX index_name 
	ON table_name (column1, column2, ...); 

CREATE INDEX idx_lastname 
	ON Persons (LastName);
```
- **CREATE VIEW**
```
CREATE VIEW view_name AS
	SELECT column1, column2, ... 
	FROM table_name 
	WHERE condition;
```
- **ALTER TABEL**
```
ALTER TABLE table_name 
	ADD column_name datatype; 

ALTER TABLE table_name 
	DROP COLUMN column_name;
 
ALTER TABLE table_name 
	ALTER COLUMN column_name datatype; 

ALTER TABLE table_name 
	MODIFY COLUMN column_name datatype;
```
- **DROP TABLE**
```
DROP TABLE table_name;
```
## Data Manipulation
To manipulante data stored in relation databases we ca use various commands such as:
- **SELECT**
```
SELECT *
	FROM users
	WHERE users.id = 42;

SELECT name
	FROM users
	WHERE age > 42
	GROUP BY surname
	HAVING sex = 'yes'
	ORDER BY name;
```
- **INSERT**
```
INSERT INTO users (name, surname, age, sex)
VALUES ('John', 'Fallout', 42, 'yes');
```
- **UPDATE**
```
UPDATE users
	SET name = 'Jon'
	WHERE Surname = 'Fallout';
```
- **DELETE**
```
DELETE FROM users
	WHERE name = 'Jon' AND surname = 'Fallout';
```
## Special Data Structures
### View
Virtual database structure that allows for selection of data from none to many tables. We can works with views as with databases, they can extract specific columns from tables, they can connect multiple tables together and they can connect to other views. We create them with a **SELECT** command as if we were asking for the data and we can use them repeatably. They work as reusable SELECT commands.
### Cursor
Virtual database structure that allows for sequential work with data entries, which we can not only read but also modify. They can use imperative approach to data manipulation unlike the declarative one with UPDATE.
### Stored Procedure
Know also as routine, virtual database structure that allows store SQL commands that can be then carried out at a later date when called for.
### Trigger
Similar to stored procedures, but instead of having to manually activate them they are activated (triggered) automatically if a certain condition is met. This condition is commonly another command getting executed such as UPDATE, INSERT or DELETE.
