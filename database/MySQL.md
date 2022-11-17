# MySQL
- Note for MySQL learning and database
- Video tutorial: https://www.youtube.com/watch?v=xiUTqnI6xk8

Table of Contents
=================

* [MySQL](#mysql)
* [Context](#context)
   * [Introduction to SQL and Database](#introduction-to-sql-and-database)
   * [MySQL](#mysql-1)
      * [Installation](#installation)
      * [MySQL Commands](#mysql-commands)

Created by [gh-md-toc](https://github.com/ekalinin/github-markdown-toc)

# Context

## Introduction

Structural Query Language (SQL)
- Language to talk to database

Database
- e.g. Excel spreadsheet

Database Management System (DBMS)
- e.g. MS SQL Server, MySQL, PostgreSQL

Database Type
- Relational Database (RDBMS)
    - Database related to other databases
- Non-relational Database

## MySQL

### Installation
MySQL Server Installation on Fedora

- Fedora Docs
    - https://docs.fedoraproject.org/en-US/quick-docs/installing-mysql-mariadb/
- In terminal
    - `sudo dnf install mariadb-server`
    - `sudo systemctl start mariadb`
    - `sudo systemctl status mariadb`

### MySQL Commands

#### Connect to MySQL Server
- In terminal
    - `mysql -u USERNAME -n REMOTE_SERVER -P PORT -p PASSWORD`
    - or `sudo mysql` if you are in local machine and no password is set

#### Commands in MySQL Server
SQL command ends with semi-colon `;`

- `show databases;`
    - List all databases
- `create database NAME;`
    - Create a new database DATABASE
- `use NAME;`
    - Use database DATABASE

#### Commands in database
SQL command ends with semi-colon `;`

- `show tables;`
    - List all tables
- `create table TABLE (id int, name varchar(255)));`
    1. Create a table call TABLE
    2. Assign first column of table with name id and its datatype int (integer)
    3. Assign second column of table with name name and its datatype varchar (string) with max length 255
- `describe TABLE`
    - Show column property of table TABLE
- `insert into TABLE values (1, "default");`
    - Insert row (in which 1st column: 1, 2nd column: "default") into table TABLE
- `select * from TABLE;`
    - Get all columns from table TABLE
- `selcct COLUMN from TABLE;`
    - Get column COLUMN from table TABLE
- `select * from TABLE where COLUMN = "CRITERIA";`
    - Select rows that their column values are "CRITERIA" in column COLUMN)
- `select * from TABLE where COLUMN = "CRITERIA_1" or COLUMN = "CRITERIA_2";`
    - Select rows that their column values are "CRITERIA_1" or "CRITERIA_2" in column COLUMN)
- `select COLUMN_N from TABLE where COLUMN = "CRITERIA_1" or COLUMN = "CRITERIA_2";`
    - Select column COLUMN_N from rows that their column values are "CRITERIA_1" or "CRITERIA_2" in column COLUMN)
- `delete from TABLE where COLUMN = "CRITERIA";`
    - Remove rows that their column COLUMN values are "CRITERIA"
- `update TABLE set COLUMN = "NEW_VALUE" where COLUMN = "OLD_VALUE";`
    - Update rows with their column COLUMN value "OLD_VALUE" to new value "NEW_VALUE"
- `select * from TABLE order by COLUMN asc/desc;`
    - Sort table TABLE with order ascending/descending with column COLUMN value
- `alter table TABLE add COLUMN COLUMN_TYPE;`
    - Add new column COLUMN to existing table TABLE with column value type COLUMN_TYPE
