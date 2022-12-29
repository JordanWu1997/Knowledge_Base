# MySQL
Note for MySQL learning and database

- Video tutorial:
    - https://www.youtube.com/watch?v=xiUTqnI6xk8
    - https://cs50.harvard.edu/x/2022/weeks/7/
    - https://www.youtube.com/watch?v=gvRXjsrpCHw
    - https://www.youtube.com/watch?v=HXV3zeQKqGY&t=13578s
    - https://www.youtube.com/watch?v=Hl4NZB1XR9c&list=WL&index=61
    - https://www.youtube.com/watch?v=7S_tz1z_5bA
- Document:
    - https://www.w3schools.com/sql/sql_ref_keywords.asp

# Context

## SQL Introduction

Structural Query Language (SQL) is the language to talk to database where data is stored (e.g. Excel spreadsheet)

Database Management System (DBMS) is that manages databases
- e.g. MS SQL Server, MySQL, PostgreSQL

Database Type
- Relational Database (RDBMS)
    - Organize data with traditional tables
        - e.g.. EXCEL sheet
- Non-relational Database
    - Organize data in non-traditional tables
        - e.g. Key-value Hash, documents (JSON, XML, and etc.), graphs

Structural Query Language (SQL) is composed by following languages
- Data Definition Language (DDL)
    - CREATE
    - ALTER
    - DROP
    - TRUNCATE
- Data Manipulation Language (DML)
    - INSERT
    - UPDATE
    - DELETE
    - MERGE
- Data Control Language (DCL)
    - GRANT
    - REVOKE
- Transaction Control Language (TCL)
    - COMMIT
    - ROLLBACK
    - SAVEPOINT
- Data Query Language (DQL)
    - SELECT

Basic SQL Operation (Data Creation/Manipulation/Query): __CRUD__
- C: CREATE (for database), INSERT (for table)
- R: READ, SELECT
- U: UPDATE
- D: DROP, DELETE (for table)

## MySQL Basic Usage

### Installation
MySQL Server Installation on Fedora

<details>

- Fedora Docs
    - https://docs.fedoraproject.org/en-US/quick-docs/installing-mysql-mariadb/
- In terminal
    - `sudo dnf install mariadb-server`
    - `sudo systemctl start mariadb`
    - `sudo systemctl status mariadb`

</details>

### Connect to MySQL SERVER
- In terminal, if no password is set
    - `sudo mysql`
- In terminal, if password is set
    - `mysql -u USERNAME -n REMOTE_SERVER -P PORT -p PASSWORD`

### Run SQL script (`*.sql`) with DATABASE
- In terminal, if no password is set
    - `sudo mysql DATABASE < SQL_SCRIPT`
- In terminal, if password is set
    - `mysql -u USERNAME -p PASSWORD DATABASE < SQL_SCRIPT`

## MySQL Data

### MySQL Datatype
1. `INT`: Integer
2. `DECIMAL(m,n)`: Float (m: total digit number, n: digit number after dot)
3. `VARSHAR(n)`: String (n: maximal length of string)
4. `BLOB`: Binary Large Object
5. `DATE`: Date (YYYY-MM-DD)
6. `TIMESTAMP`: Timestamp (YYYY-MM-DD HH:MM:SS)

### MySQL Data Component
1. Primary Key: Keys that repents data in current table
    - Primary key should be __UNIQUE__ and __CANNOT BE NULL__
    - Primary key can be composed by multiple keys if one key cannot represent data uniquely
2. Foreign Key: Keys that represents relations between current table and other tables
3. Attribute: Properties that owns by data (e.g. columns in tables)

## MySQL Command - DATABASE
SQL commands should all be CAPITALIZED and end with semi-colon `;`

- `SHOW DATABASES;`
    - List all databases
- `CREATE DATABASE database;`
    - Create a new database `database`
- `USE database;`
    - Use database `database`
- `DROP DATABASE database;`
    - Remove database `database`

## MySQL Command - TABLE
SQL commands should all be CAPITALIZED and end with semi-colon `;`

### SHOW/DESCRIBE Command
`SHOW`: List all available table, `DESCRIBE`: Show information of attributes in table

- `SHOW TABLES;`
    - List all tables
- `DESCRIBE table`
    - Show attribute (column) property of table `table`

### CREATE TABLE
Create table

- `CREATE TABLE table (id INT, name VARCHAR(255)));`
    1. Create a table call `table`
    2. Assign first column of table with name id and its datatype INT (integer)
    3. Assign second column of table with name name and its datatype VARCHAR (string) with max length 255
- `CREATE TABLE table (id INT UNIQUE, name VARCHAR(255) NOT NULL)`
    - Create table `table` with
        - Column ID with datatype INT and must be unique
        - Column name with datatype VARCHAR and must not be NULL
- `CREATE TABLE table (id INT, PRIMARY KEY id)`
    - Create table `table` with primary key id
- `CREATE TABLE table (id INT AUTO_INCREMENT, PRIMARY KEY id)`
    - New row id will be automatically increase when new row is inserted

### CREATE INDEX for Faster Querying
- `CREATE INDEX`

### Constraints
Constraints for values. These can be changed by `ALTER` with `ADD/DROP CONSTRAINT` after table is `CREATE`

#### Constraints for Attribute
- `NOT NULL`: Make sure the input value __CANNOT be NULL__
- `UNIQUE`: Make sure that input value __MUST be UNIQUE__
- `PRIMARY KEY`: Attribute that uniquely identifies each row in table (MUST be __NOT NULL__ AND __UNIQUE__)
- `FOREIGN KEY`: Attribute that refers to attribute of other tables
    - If corresponding __FOREIGN KEY is UNAVAILABLE__: `ON DELETE`
        - `ON DELETE SET NULL`: Set value to NULL
        - `ON DELETE CASCADE`: Remove entire row (use case: PRIMARY key which can not be NULL is composed by FOREIGN key)
        ON UPDATE
- `AUTO_INCREMENT`: Increase integer value by 1 when new row is inserted
    - `AUTO_INCREMENT=100`: Increment of integer value starts from 100 when new row is inserted
    - `AUTO_INCREMENT(100,5)`: Starts from 100, increase integer value by 5 when new row is inserted

#### Set Default Value and Check Constraint
- `DEFAULT`: Set default values for attributes. This can be changed by `ALTER` with `SET/DROP DEFAULT`
    - Syntax: `attribute datatype DEAULT default_value `
- `CHECK`: Check if input value satisfies the condition `condition`
    - Syntax: `CHECK (contidtion)`

### DROP/TRUNCATE/ALTER Command
Define data structure with drop/truncate/alter command to the table

- `DROP TABLE table`
    - Remove table `table`
- `TRUNCATE TABLE table`
    - Remove all elements in table `table`
- `ALTER TABLE table ADD column column_type;`
    - Add new column `column` to existing table `table` with column value type `column_type`
- `ALTER TABLE table DROP column`;
    - Remove column `column` from table `table`
- `ALTER TABLE table MODIFY column datatype`;
    - Change datatype of column `column` to `datatype`

### INSERT/UPDATE/DELETE command
Manipulate (insert/update/delete) data attribute in table

- `INSERT INTO table VALUES (1, "value");`
    - Insert row (in which 1st column: 1, 2nd column: "value") into table `table`
- `INSERT INTO table(id, value) VALUES (1, "value");`
    - Insert row with assigned columns `id` and `value` into table `table`, other columns will be filled with default value (if there is one) or `NULL`
- `UPDATE table SET column = "new_value" WHERE column = "old_value";`
    - Update rows with their column `column` value "old_value" to new value "new_value"
- `DELETE FROM table WHERE column = "criteria";`
    - Remove rows that their column `column` values are "criteria"

VALUE DEFAULT

### SELECT command
Select data from table

- `SELECT * FROM table;`
    - Get all columns from table `table`
- `SELCCT column FROM table;`
    - Get column `column` from table `table`
- `SELECT DISTINCT(column) FROM table;`
    - Select unique value in column `column` from table `table`
- `SELECT COUNT(title) FROM table;`
    - Calculate counts of title in table `table`
- `SELECT * FROM table LIMIT 10;`
    - Show only first 10 rows in table `table`
- `SELECT * FROM table ORDER BY column ASC/DESC;`
    - Sort table `table` with order ascending/descending with column `column` value

SELECT * FROM new_table AS SELECT * FROM old_table;
INSERT INTO new_table SELECT * FROM old_table;

### ORDER BY

### GROUP BY
Aggregate function functions after group by
GROUP BY
HAVING: Same as where but works after group by

### Aggregate Function
- `COUNT`: Count number of occurrence
- `AVG`: Calculate average
- `SUM`: Calculate sum
- `MAX`: Find maximal value
- `MIN`: Find minimal value

### Alias
SELECT AS

### SELECT command + WHERE condition
Wild cards for LIKE: `%`: zero or multiple characters, `_`: one character

- `SELECT column FROM table WHERE column LIKE "value"`
    - Select rows that have value `value` in column `column` from table `table`
    - `LIKE`: case-insensitive command
- `SELECT column FROM table WHERE column LIKE "%value%"`
    - `%`: 0 or more characters just like `*` in regex
- `SELECT * FROM table WHERE column = "criteria";`
    - Select rows that their column values are "criteria" in column `column`)
- `SELECT * FROM table WHERE column = "criteria_1" OR column = "criteria_2";`
    - Select rows that their column values are "criteria_1" or "criteria_2" in column `column`)
- `SELECT column_n FROM table WHERE column = "criteria_1" OR column = "criteria_2";`
    - Select column `column_n` from rows that their column values are "criteria_1" or "criteria_2" in column `column`)
- `SELECT column_n FROM table WHERE column IN ("criteria_1", "criteria_2");`
    - Select column `column_n` from rows that their column values are "criteria_1" or "criteria_2" in column `column`)

### Subquery
()

### EXISTS command

### Logical Operator
- `AND`:
- `OR`:
- `NOT`:
- `LIKE`: Search specific pattern in string
- `IN`:
- `BETWEEN`
- `ANY`
- `ALL`
- `SOME`

`REGEXP`

### Set Operator for Rows
UNION
UNION ALL
EXCEPT
INTERSECT

The attribute type must be the same

### Arithmetic  Operator

### Set Operator for Attributes

### Join Operator
JOIN ON
JOIN USING

INNER JOIN: Intersection
LEFT JOIN: Rows of left table and matched rows of right table (value is set to NULL if there is no match)
RIGHT JOIN: Rows of right table and matched rows of left table (value is set to  NULL if there is no match)
FULL JOIN: Rows of left table and right table (value is set to NULL is there is no match)
CROSS JOIN
NATURAL JOIN

SELECT INTO
INSERT INTO SELECT

### Case Statement

### View
