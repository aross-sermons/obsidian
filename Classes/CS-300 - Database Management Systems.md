---
title: CS-300 - Database Management Systems
parent:
  - "[[Class]]"
aliases: 
tags:
  - cs-class
  - dense-note
---
### CS-300 - Database Management Systems
### Class Overview
**Instructor** - Andrew Karem, Ph.D.
- akarem@bellarmine.edu
- 502-468-1841
- Office Hours - M/W 11 AM to 12:30 PM
**Location** - Pasteur 106
**Time** - T/R 3:05-4:20 PM
## Dictionary
### Relational Model Terms
- Attribute
- Domain
- Relational Model
- Relation
- Constraints
- Referential Integrity Constraints
### SQL Terms
- Table - Equivalent to a relation.
- Row - Equivalent to a 
- Column
## Day One
**Terminology and Abbreviations**
- RM/RDM - Relational (Data) Model
- RDBMS - Relational Database Management System
- SQL - Structured Query Language
**MySQL**
	MySQL is an open-source RDBMS system.
- MySQL will provide hands-on experience with databases in this course.
- Some problems in this course require MySQL.
## Lecture 1
**Basic Definitions**
- **Database** - A collection of related data.
- **Data** - Meaningful information that can be recorded.
- **Mini-World** - Information about the real world that is stored in a database.
- **Database Management System** - A software package or system used to create and maintain a database.
- **Database System** - The DBMS sofware *and* the data itself.
**Typical DBMS Functionality**
- **Define** - Define a database in terms of its data types, structures, and constraints.
- **Consrtuct** - Load the initial database contents on a secondary storage medium.
- **Manipulate** - Access and modify the data in the database.
- **Processing and Sharing** - Concurrent clients using the database and its data.
**Application Activities Using a Database**
	Applications interact with a database by generating **Queries** and **Transactions**. Queries access different parts of data and return a result to a request. Transactions may read, update, or generate data.
## Lecture 2
### Database Characteristics
**Self-describing** - Meta data, what kind of data is represented.
- A **catalog** stores the description of a database (data structures, types, constraints).
- This description is called **meta-data**.
- Meta-data aides the DBMS in interacting with other applications.
**Program-data Independence** - Insulation between programs and data.
- Allows databases to change their content and organization without having to change all DBMS programs.
**Data Abstraction**
- A **data model** is used to hide details from users. It presents the user with a conceptual view of the database.
- Programs refer to data models rather than specific storage details.
**Multiples Views of Data**
- Certain users only see the information relevant to them.
**Concurrent Transactions** - Multiple users editing data at once.
- **Concurrency Control** - A mechanism within the DBMS which guratnees that each transaction is correctly executed.
- **Recovery** - Each transaction has a permanent record stored.
- **Online Transaction Processing (OLTP)** - Allowing many concurrent transactions to be computed continuously.
### Database Users
**Two Types**
- **Actors on the Scene** - Those who use and control database content and those who design, develop, and maintain database applications.
- **Workers Behind the Scene** - Those who design and develop the DBMS software and related tools.
**Actors on the Scene**
- **Database Administrators** - Responsible for...
	- Authorizing access to the database.
	- Coordinating and monitoring database use.
	- Acquiring software and hardware resources.
	- Monitoring efficiency.
- **Database Designers** - Responsible for...
	- Define the content, structure, constraints, and functions of the database.
	- Communicate with end-users to understand and meet their needs.
**Workers Behind the Scene**
- **System Designers and Implementors** - Responsible for...
	- Designing and implementing DBMS packages.
	- Ensuring the DBMS can interface with other applications.
- **Tool Developers** - Responsible for...
	- Designing and implementing software used to model databases, analyze performance, create user interfaces, generate test data, and more.
- **Operators/Maintenance Personnel** - Responsible for...
	- Maintaining the software and hardware of the database environment.
**End Users**
- **Casual** - Access database occasionally.
- **Naive or Parametric** - Make up a large portion of the end-user population.
	- Use well-defined functions as **canned transactions**.
	- May include mobile app users, bank tellers, reservation clerks, social media users.
- **Sophisticated** - Use tools in the form of software packages.
	- Business analysts, scientists, engineers, and others who are familiar with the system.
- **Stand-alone** - Maintain a personal database.
	- A user of a tax program.
	- A database of personal photos and videos.
### In-Class Activity
**What's Wrong with the Database?**
- Different formats for firstname-lastname.
- Different time/date formats.
- Some shell types are "none" or NULL, which may conflict.
- Descriptions aren't formatted similarly.
### Database Advantages
**Securing Data**
- Functionality for backup and recovery services.
- Providing heriarchical access to different users.
- Managing encrypted data.
**Visualizing or Representing Data**
- Visualize complex relationships.
- Model data in many different ways.
**Efficiency**
- Query optimization.
- Controlling redundancy in data storage.
**Developing and Enforcing Standards**
- **Standards** - Item names, display formats, report structures, meta-data, website designs, and more.
- A good database can help develop standards for an organization to streamline future development.
**Flexibility**
- Structure may change over time to meet new needs.
### Data Models
**Data Model** - A set of concepts to describe a database. Includes...
- Descriptions of the **structure** of the database.
- The **operations** that may be performed on the database.
- The **constraints** that limit those operations.
**Data Model Constructs** - Defind the structure of the database.
- Elements, their data types, and groups of elements.
**Data Model Operations**
- Basic model operations (insert, delete, update).
- User-defined operations (sompute student gpa).
**Categories of Data Models**
- **Conceptual Data Models** - High-level, semantic.
	- Provide concepts that are similar to how users percieve data.
	- Also called entity-based or object-based data models.
- **Pysical Data Models** - Low-level, internal.
	- Describe how data is stores on the hardware.
- ==**Implementation Data Models**== - Representational.
	- 
- ==**Self-Describing Data Models**==
### Schemas Vs Instances
**Database Schema** - The description of a database.
- Includes database structure, data types, and constraints.
**Schema Diagram** - An illustrative display of a database schema.
**Schema Construct** - A componend of the database schema.
- Includes tables, objects like students and courses, and data types.
**Database State** - The actual data stores in a database at any given moment.
- Also called a database instance.
- **Initial Database State** - The state of the database when first loaded.
- **Valid State** - A state that satisfies the structure and constraints of the database.
### Three-Schema Architecture
**Three Levels** - From top to bottom...
1. **External Schema** - Describe the various user views.
2. **Conceptual Schema** - Describe the structure and constraints of the whole database.
3. **Internal Schema** - Describe physical storage structures.
### Data Independence
**Logical Data Independence** - The capacity to change conceptual schema without having to change external schema.
- Ex: Adding new and unassociated tables should not effect user views.
**Physical Data Independence** - The capacity to change internal schema without having to change conceptual schema.
## Lecture 2
### Server Architectures
**What are 2-Tier Servers?** - Client-server relations in whcih one or multiple servers host content for one or more clients.
**What are 3-Tier Servers?** - Client-server relations with a translation layer in-between them meant to format and check communications.
### Relation Models
**Relations** - A relation is a mathematical concept based on sets.
- Proposed by Dr. E.F. Codd of IBM Research in 1970.
- Informally, a relation looks like a table of values.
- Contains a set of rows, called **tuples**.
- Each column has a header called an **attribute**.
**Schema** - The description of a relation.
- Denoted by $R(A_1, A_2, ...A_n)$
- R is the name of the relation and A are its attributes.
**Domain** - A specific definition of a type of data.
- Has a data-type and format.
- Ex: US Phone Numbers: (ddd)ddd-dddd
**Tuples** - Enclosed in `<...>` brackets.
- Each value is derived from a domain.
- A relation is a set of tuples.
- Tuples are not ordered, even if they appear to be.
**Keys** - A value of a tuple that acts as a unique identifier.
- If a row id or sequential number list is assigned as a key, that is called an **artificial** or **surrogate key**.
**State** - Any possible combination of attributes and tuples.
**Relation State** - The subset of all possible tuples in a given relation.
- Ex: lastname = char (20), firstname = char(20); $26^{20} \cdot 26^{20}$
### Constraints
**Constraints** - Determine which values are and aren't permissible in a database.
- The following three constraints are used in relational models.
**Key Constraints**
**Entitiy Integrity Constraints**
**Referential Integrity Constraints**

## Lecture 3
### Introduction to SQL
**SQL** - Structured Query Language
- A standardization of the relational data model.
- Establishes queries and syntax for working with relational models.
**History**
- Developers: Raymond Boyce, Donald Chamberlin
- Stems from relational predicate (tuple) calculus, proposed initially as a language called SQUARE.
- The name SQL comes from the word "sequel".
- IBM couldn't copyright "sequel", so we have SQL.
**SQL Features**
- Data Definition
- Data Manipulation
- Transaction Control
- Indexing (not this class)
- Security Specificationsz (not this class)
- Distributed Database Support (not this class)
**Terminology**
- **Table** corresponds with the relational term relation.
- **Row** corresponds with the relational term tuple.
- **Column** corresponds with the relational term attribute.
### Schema and Catalog Concepts
**SQL Database**
- Identified by a database/schema name.
- Includes descriptors for each element.
**Catalog**
- A named collection of SQL databases.
**Database Elements**
- Tables, constraints, views, domains, etc.
**Syntax**
- Every SQL statement ends with a semicolon.
### SQL Elements
**Fundamental Constraints**
- **Key** - Duplicate primary key values cannot exist in two rows within a table.
- **Entitiy Integrity** - A primary key value cannot be null.
- **Referential Integrity** - The foreign key must have a value that is already present as a primary key in the referenced table.
**Primary Keys**
- May defined as either...
	- `SSN INT PRIMARY KEY, ...`
	- `SSN INT, ... PRIMARY KEY(SSN)`
	- BUT the first method does not work for composite keys.
- Primary keys can't be null. Using `NOT NULL` is not required but recommended.
- Every table in this class must have a primary key.
**Secondary Keys** - Also known as candidate keys.
- Can be simple (1 attribute) or composite (2 or more attributes).
- Secondary keys include the `UNIQUE` keyword.
**Foreign Keys**
- Used to create referential integrity constraints.
- May be defined as...
	- `SSN INT, ... FOREIGN KEY(SSN) REFERENCES <TABLE>(<ATTRIBUTE>)`
	- Cannot be defined in an attribute's definition.
	- Must be established in the referencing table.
- Forgein keys may reference attributes from the same table.
**Naming Constraints** - Constraints can be named using the CONSTRAINT keyword.
- `CONSTRAINT FKssn FOREIGN KEY(ssn) REFERENCES <TABLE>(<ATTRIBUTE>)`
## Session 6
### Database Queries
**What is a Database Query?** - A command or script dispatched to a DBMS intended to retrieve information about or stored in the database.
**Statement v Clause**
- **Statement** - A complete command executable by a DBMS.
- **Clause** - A component of a statement.
**SELECT Statement** - Fundamental database query statement.
- Can be combined with clauses to create a more specific request.
**SELECT Query Structure**
- SELECT -> FROM -> WHERE -> GROUP BY -> HAVING -> ORDER BY
- But can be as simple as SELECT -> FROM
## Session 7
### JOINs
**JOINs In The FROM Clause**
## Session 10
### UPDATE Statements
**UPDATE Sytnax**
```
UPDATE <table_name> # The table to update
SET <column_name>=<new_value> # The column to update and value to set
[WHERE <where_condition>] # Optional where conditions
```
**UPDATE Syntax Notes**
- Multiple SET statements can be used in a comma-separated list.
- Omittin WHERE will apply the update to all rows in the given table.
- A simple way to update a single row is to use a key in the WHERE condition.
**UPDATE Concerns**
- Modifying a column that is referenced as a foreign key can break connections.
**ON UPDATE...** - The answer to UPDATE concerns.
- ...SET NULL - Sets referencing columns to NULL on update.
- ...SET DEFAULT - Sets referencing columns to a default value on update.
- ...CASCADE - Sets referencing columns to the updated value.
### Sentinel Rows
## Session 14 - Database Design and ER Basics
### Phases of the Database Design Process
**Step 1: Requirements Collection and Analysis Process**
- Establishing what, when, and how information needs to be processed.
- Includes concerns related to data collection.
- May consist of meeting with clients, dev teams, and other interested parties.
**Step 2: Conceptual Design**
- Consolidating the requirements from step 1 into a coherent construction plan.
- Synthesize a **high-level schema**, which includes the various external schemas as well as a high-level view of the logical schema.
- Includes specific entities and relationships.
**Step 3: Logical Design**
- Breaking apart the high-level schema into an implementation-ready detail set.
- Requires the creation of documentation and/or diagrams.
### Conceptual Design Methods
**Entity Relationship (ER) Diagrams**
**Enhanced Entity Relationship (EER) Diagrams**
## Session 15 - ER Diagrams in Depth
### Overview of the ER Model
**Three Main Concepts**
- Entities - Their types, and their sets
- Attirbutes - Simple, composite, and multivalued
- Relationships - Bind two or more entities together
### Relationships in ER Models
**Relationships** - A relationship related two or more distinct entities with a specific meaning.
- Ex: EMPLOYEE John Smith **manages** DEPARTMENT Research.
**Relationship Types** - Relationships of the same type are grouped or typed into a relationship type.
- Ex: MANAGES relationship describes the previous example.
