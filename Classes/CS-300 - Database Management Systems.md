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
**Database Elements**
- Tables, constraints, views, domains, etc.
**Syntax**
- Every SQL statement ends with a semicolon.
### Statements
**`USE <DATABASE_NAME>`** - Specifies a default database for future commands to use.
- Not required, but helpful for avoiding repeatedly referencing a database that will be interacted with regularly.
**`CREATE TABLE <TABLE_NAME>`** - Creates a new table with the provided name and columns.