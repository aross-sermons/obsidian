---
title: SQL
parent:
  - "[[Cheat Sheet]]"
aliases: 
tags:
---
## Dictionary
### SQL Terms
**Statement v Clause**
- **Statement** - A complete command executable by a DBMS.
- **Clause** - A component of a statement.
## Syntax
### Line Endings
**Semicolon Tails** - Every SQL statement ends with a semicolon.
## Operators
###
## SQL Server
### Creating Databases
**Create a New Database**
	`CREATE DATABASE <database_name>;`
**Drop an Existing Database**
	`DROP DATABASE <database_name>;`
**Change Target Database** - All following commands will target this database.
	`USE <database_name>;`
**Create a New Schema**
	`CREATE SCHEMA <schema_name>;`
**List All Databases**
	`SELECT * FROM sys.databases;`
### Creating Tables
**Create a New Table** - Tables have attributes and clauses in the form of a comma-separated list enclosed by the table's parentheses.
	`CREATE TABLE <table_name> ([table_parameters]);`
**Drop an Existing Table**
	`DROP TABLE <table_name>;`
**List All Tables**
	`SELECT * FROM sys.tables;`
**Get Table Information**
	`exec sp_help 'table_name;'`
### Table Parameters
**Creating an Attribute** - An attribute, or column, has a name and a domain. The domain is the range of valid values a tuple, or row, can have for that attribute.
```
CREATE TABLE <table_name> (
	<attribute 1> [domain],
	<attribute 2> [domain]
);
```
**List of Common Data Type Domains**
- `CHAR(n)` - A fixed length string of `n` characters where $0 \le n \le 255$.
- `VARCHAR(n)` - A variable length string of `n` characters where $0 \le n \le 65535$.
- `TEXT(n)` - A string with a maximum length of 65535 bytes.
- `BIT(n)` - A bit or collection of bits of length `n` where $1 \le n \le 64$.
## SQL Queries
**Order** - When writing a query, it should follow the format:
1. SELECT
2. FROM
3. \\\[WHERE]
4. \\\[GROUP BY]
5. \\\[HAVING]
6. \\\[ORDER BY]
### SELECT
**Use** - Select data from a database.
**Syntax** - `SELECT <column1>` with optional additional columns separated by commas.
**Example**
```
SELECT CustomerName, City
FROM Customers;

# Will return a table containing the CustomerName and City
# of each row in Customers
```
**Tips**
- Select all with `SELECT * FROM <table>`
### FROM
**Use** - Specifies which table to select or delete data from.
- Includes JOIN statements (next part).
**Syntax** - `FROM <table>`
**Example**
```
SELECT CustomerName, City
FROM Customers;

# Will return a table containing the CustomerName and City
# of each row in Customers
```
### (INNER) JOIN
**Use** - Returns records that have matching values in both tables.
**Syntax** -  `JOIN <to_table> ON <from_table.column> = <to_table.column>` where both columns are the same foreign key.
**Example**
```
SELECT CustomerName, Orders.OrderID
FROM Customers
JOIN Orders ON Customers.CustomerName = Orders.CustomerName;

# If Orders has a row with the same CustomerName as any given row from # Customers, those rows will be joined and the SELECT will work for
# both values.
```
**Tips**
- More JOINs in the main section below.
### WHERE
**Use** - Filters records to extract only those that meet a specified condition.
**Syntax** - `WHERE [conditions]`
**Example**
```
SELECT *
FROM Customers
WHERE Country = "Mexico";

# Will return every row with the Country value matching "Mexico"
```
**Tips**
- Also used in UPDATE, DELETE, and other statements.
- Uses normal operators (-, >, <, >=, <=, !=)
- **BETWEEN Operator** - Between a certain range.
	- `WHERE Price BETWEEN 50 AND 60;`
- **LIKE Operator** - Search for a pattern.
	- `WHERE City LIKE '%s';`
- **IN Operator** - Specify multiple possible values for a column.
	- `WHERE City IN ('Paris', 'London');`
### GROUP BY
**Use** - Groups rows that have the same values into summary rows.
**Syntax** `GROUP BY [column_names]`
**Example**
```
SELECT CustomerID, Country
FROM Customers
GROUP BY Country;

# This will sort the CustomerIDs by Country
```
### HAVING
**Use** - 
## JOINS
### (INNER) JOIN
**Use** - Returns records that have matching values in both tables.
**Syntax** -  `JOIN <to_table> ON <from_table.column> = <to_table.column>` where both columns are the same foreign key.
**Example**
```
SELECT CustomerName, Orders.OrderID
FROM Customers
JOIN Orders ON Customers.CustomerName = Orders.CustomerName

# If Orders has a row with the same CustomerName as any given row from # Customers, those rows will be joined and the SELECT will work for
# both values.
```
### LEFT (OUTER) JOIN
**Use** - Returns all records from the left table and the matched records from the right table.
**Syntax** - `LEFT JOIN <to_table> ON <from_table.column> = <to_table.column>`