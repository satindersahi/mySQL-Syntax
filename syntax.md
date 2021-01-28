## How to log in to MySQL with Terminal or CMD
```
> mysql -u root -p;
```

After running this command, you will need to enter your MySQL password.
***

## How to "SHOW USERS"

In order to show all MySQL users, we must run the following querie in mysql root:

``
> SELECT user FROM mysql.user;
```
this command will display list of all the users.

## How to CREATE USER

```
> CREATE USER 'username'@'localhost' IDENTIFIED BY 'password';
```
***

## How to GRANT PRIVILEGES, Show granted privileges and remove.

After Creating New User, run this command to grant ALL PERMISSIONS to the user:

```
> GRANT ALL privileges
ON databasename.table_name TO username@server;
```
***
### To check current Privileges.

```
> SHOW GRANTS FOR 'username'@'localhost';
```
***

### How to Remove Privileges.
```
> REVOKE permission ON database.table FROM 'user'@'localhost';
```
***

## How to "SHOW", "DELETE", "CREATE", and "SELECT" databases

To Show Databse -> all commands run in mysql root
```
> SHOW DATABASES;
```

To Delete Databse
```
> DROP DATABASE databasename;
```

To Create Dtabase
```
> CREATE DATABASE databasename;
```


To select a database:
```
> USE databasename;
```
***

## How to create a "TABLE" with columns and data types

**To create a table**, we use the following syntax:
```
> CREATE TABLE tablename (
> column_name DATATYPE,
> column_name DATATYPE,
> );

Ex - 
> CREATE TABLE test (
> name VARCHAR(255),
> id INT,
> );

```
***
## How to "SHOW", "DELETE", and "DROP" tables


 To Show tables:
```
> SHOW TABLES;
``` 

To DROP or delete a table:
```
> DROP TABLE tablename;
```

***
## How to insert rows ( single and multiple )

To insert rows into a table,
```
> INSERT INTO tablename (column1, column2) 
> VALUES ('string', integer);

Ex-

> INSERT INTO test(name, id)
> VALUES ('ron',6);
```
***

## How to 'SELECT' with the 'WHERE' clause 

```
> SELECT column1, column2 
> FROM tablename 
> WHERE condition;

Ex-
> SELECT * FROM tablename
> WHERE condition;
```
***
## How to 'DELETE' an individual row

```
> DELETE FROM tablename 
> WHERE condition;

**Example:**

> DELETE FROM test 
> WHERE id = 6;
```
***
## How to 'UPDATE' a row

```
> UPDATE tablename
> SET columnname = value,
> columnname2 = value
> WHERE condition;
```
***
## How to add a new column and modify it
```
> ALTER TABLE tablename
> ADD columnname datatype;
```
***
## modify a column:
```
> ALTER TABLE tablename
> MODIFY columnname datatype;
```
***
## How to 'ORDER BY' and use 'DISTINCT'
```

> SELECT column1, column2 
> FROM tablename 
> ORDER BY column1 ASC|DESC;
```

**Example:**
```
> SELECT * 
> FROM test 
> ORDER BY age ASC;
```

***
## Use Distinct -
```
> SELECT DISTINCT column1, column2 FROM tablename;

Example-

> SELECT DISTINCT id, name FROM test;
```
## How to concatenate columns

To concatenate columns - 
```
> SELECT  CONCAT (column1, column2) 
> FROM tablename;
```
***

## How to use 'LIKE' to search

```
SELECT Col_name1, col_name2, .. , col_nameN
FROM "Table_name"
WHERE "Col_name1" LIKE "value"

example- 

SELECT * FROM LOAN_034
WHERE UPPER (NAME) LIKE R%;

```

***

## How to select using 'IN' or 'NOT IN' and 'BETWEEN'

The 'IN' clause can be used -
```
> SELECT column1, column2
> FROM tablename
> WHERE column1 
> IN (value1, value1);

Example:

> SELECT *
> FROM test
> WHERE id
> IN (4,6);
```

***
## How to create and remove indexes

```
> CREATE INDEX indexname
> ON tablename (columnn1, column2);
```
***

## Primary and Foreign Keys

**Primary Keys** and **Foreign Keys** are used to specify the information between tables.
```
CREATE TABLE dbo.Person
(
Pk_Person_Id INT IDENTITY PRIMARY KEY,
Name VARCHAR(255),
EmailId VARCHAR(255),
);

CREATE TABLE dbo.PassportDetails
(
Pk_Passport_Id INT PRIMARY KEY,
Passport_Number VARCHAR(255),
Fk_Person_Id INT UNIQUE FOREIGN KEY REFERENCES dbo.Person(Pk_Person_Id)
);
```
***

## How to use inner join

An **inner join** may be used to combine rows of data.
```
> SELECT test.name, test2.age
FROM table1
INNER JOIN table2
ON test.id = table2.id;

```
***

## How to JOIN Multiple Tables
```
SELECT * FROM TABLE_A A
FULL JOIN TABLE_B B
ON A. Common_COLUMN =B. Common_COLUMN
```
