# Types of databases
- Traditional numeric and textual databases
- Multimedia DB
- Geographic Information Systems (GIS)
- Biological and genome DB
- Data warehouses
- Mobile DB
- Real-time/active DB

# Database management system (DBMS)
- Sits between the database application and the database in a layered model
- Defines a database in terms of data types, structures, and constraints
- Constructs or loads the database contents to a storage medium
- Manipulates the database
  - Retrieval: Read
  - Modification: Insertion, deletion, update
- Keeps data valid and consistent even with concurrent usage by multiple uses
- Protects data from unauthorized access
- Active processing for internal actions, such as triggers and stored procedures
- Presentation of data
- Maintenance of the database: backups

# Conceptual data model
- Defines the miniworld which are the main concepts and relationships of the data

# The database approach
- Meta-data: descriptions about structures, types, and constraints
- Program-data independence: allows changes to the database without having to change the accessing programs
- Data abstraction: Hides storage details
- Supports multiple views
- Shares data to reduce data redundancy
- Multi-user transaction processing
  - Online Transaction Processing (OLTP) processes concurrent transactions
- Restricts access to data
- Optimizes queries
- Keeps backups
- Enforces standards, such as naming systems
- Compared to direct file system IO, DBs reduce app dev time
- Flexibility for evolving structures and relationships

# Database users
- Actors on the scene - Users who are interested in the data
  - DB administrators - controls access
  - DB designer - designs the structures and relationships of the DB
  - End user - those who use the DB for general use, from customers to marketing
  - System analysis and app developers - analysts research user requirements and devs implement the specifications
- Workers behind the scene - Maintains the DB and do not need the data contents
  - DBMS system designers
  - Tool developers
  - Maintenance

# History of databases
- Hierarchical and network model
  - IMS system
  - Procedural language
- Relational model
  - Based on mathematical models to abstract the storage details
  - Declarative
- Object-oriented
  - Not common today
- NOSQL
  - Unstructured data with flexible models of tx processing

# When not to use a DBMS
- Overhead costs such as for maintenance and training
- Real-time or embedded applications

# Data models
- Conceptual
  - Concepts are similar to how humans think
- Physical
  - Describe how data is to be stored on a medium
- Implementation
  - Concepts that are between physical and conceptual, such as relational data models
- Self-describing
  - Includes meta-data with the data, such as in NOSQL

# Schemas and state
- Schema: Description of a database, can be represented with a schema diagram
- Database state: Data stored at a moment in time, aka snapshot
- States correspond to specific schemas

# Three-schema architecture
- Internal schema: Physical level
- Conceptual schema: Structures and contraints of the whole database
- External schema: User views that expose only the data that a user is interested in

# Data independence
- Logical data independenece: Allows changes to conceptual schema without having to change external schema
- Physical data independence: Allows changes to internal schema without changing the conceptual schema

# Types of DBMS languages
- Data definition language (DDL)
  - Creates and modifies database objects
  - Specifies the conceptual schema, and some DDLs define internal and external schema
- Data manipulation language (DML)
  - Specifies ACID operations
  - High level: Set oriented and declarative
  - Low level: Procedural

# 2-tier client-server architecture
- Client
  - Interface for the DBMS
  - Connected to servers through a network
- Server
  - Houses the database
  - Processes queries and transactions

# 3-tier client-server architecture
- Common for web apps
- Between the client and server is an application layer
  - Stores the connectivity software and businesss logic
  - Acts as a security barrier

# Distributed DBMS
- Data is stored at multiple sites
- Homogenous DDBMS: Uses the same DBMS software at all sites
- Heterogeneous DDBMS: Uses different DBMS software at sites
- Federated DBMS: Different and autonomous DBMSs connected by a middleware

# Relational data model
- Table = Relation
- Column name = Attribute
- Set of all possible column values = Domain
- Row = Tuple
- Table definition = Relation schema
- Table state = Relation state

# Constraints
- Inherent/implicit constraint: Based on the data model/type
- Schema-based/explicit constraint: Expressed in the schema
  - Entity integrity constraint: No primary key value can be null.
  - Referential integrity constraint: A reference must point to an existing tuple
- Application-based/semantic constraint: Enforced by application programs

# Key
- A key has two properties:
  - Two unequal tuples cannot be associated with an equal key set (It is a superkey)
  - It is not possible to remove any attribute in the key set without losing the first property (It is a minimal superkey)

# Entity relationship diagram
- Rectangle = Entity
- Double rectangle = Weak entity (Cannot be identified by its attributes alone)
- Oval = Attribute
- Double oval = Multivalued attribute
- Dotted oval = Derived attribute (Value depends on other attributes)
- Underline = Primary key
- Dotted underline = Partial key
- Diamond = Relationship (Connects two strong entities)
- Double diamond = Identifying relationship (Connects a weak entity)
- Line = Partial participation (Not all entities are involved in the relationship)
- Double line = Total participation (All entities are involved in the relationship)
- A line that passes through a circle, with a "U" on the line = Specialization

# Crow's foot notation
- Symbols
  - O = Zero
  - | = One
  - < = Many
- Order of symbols
  - The symbol closest to the origin indicates multiplicity, or the maximum number in the relationship
  - The second symbol is the cardinality, or the minimum number in the relationship

# Enhanced Entity-Relationship Modeling
- A local attribute, which is an attribute for only the subclass, may be connected to the subclass
- Specialization constraint
  - Disjoint constraint
    - An entity can only be a member of one subclass only for a given specialization
    - Has a "d" symbol in the circle
  - Overlapping constraint
    - An entity may be a member of one or more subclasses in a specialization
    - Uses a "o" symbol
  - Total constraint
    - Every entity in the superclass must be a member of a subclass
    - Denoted by a double line
  - Partial constraint
    - An entity may or may not belong to a subclass
    - Denoted by a single line
- Specialization: The process of defining a set of subclasses of a superclass
- Generalization: The process of combining several classes with a common superclass
- Hierarchy: A subclass only has one superclass
- Lattice: A subclass can have one or more superclasses
- Union type: A class that can represent different subclasses. Just like C unions. Uses the "u" symbol.

# Mapping extended relations
- Regular entity: Create a record that include all attributes and choose an attribute as the primary key
- Weak entity: Create a record R for the entity and add a foreign key that links to the owner entity. The primary key of R is the combination of the foreign key and partial key of R.
- Binary 1:1 relation types
  - Use a foreign key
  - Merge the entities into a record
  - Create a third record to link the two entities
- 1:N relation types: Use a foreign key in the N-side of the relationship that links to the single primary key
- M:N relationship type: For each relationship R, create a new record S to represent R. S contains the foreign keys of both entities participating in the relationship.
- Multivalued attribute: Create a record R for each item. R includes a foreign key that links to the record containing the multivalued attribute. The primary key of R is the combination of the foreign key and the item.
- N-ary relationship type: For each relationship, create a record S. S includes foreign keys of all participating entities. S also includes any attributes of the relationship.
- Several options for mapping specializations and generalizations
  - Create a superclass record. Also create record types that contains the relationship attributes for each subclass and a foreign key attribute that links to the superclass record. The primary key for the subclass is the foreign key. (Works for any type of specializations.)
  - Create a record type for each subclass, which includes all subclass and superclass attributes. (Total disjoint relationships only)
  - Create a single record type that includes the attributes for each subclass, and an additional attribute for determining which subclass type the record represents. Like a C++ variant. (For any type of specialization)
  - Like the last option, but instead of using a single attribute to indicate type of subclass, there are N boolean attributes where N = number of subclass types. The boolean attributes are flags that indicate membership of different subclasses.
- Union type: Create a record type for each union category, which has a foreign key linking to the superclass.
- Steps for mapping models
  1. Create tables for the entities
  2. Create tables for the weak entities
  3. Create tables for the relationships
  4. Identify all primary keys
  5. Link the foreign keys

# SQL
- `CREATE DATABASE` and `CREATE SCHEMA` are exactly the same
- `CREATE TABLE` example
  ```
  CREATE TABLE orders (
      order_id int NOT NULL,
      user_id int,
      PRIMARY KEY (order_id),
      FOREIGN KEY (user_id) REFERENCES users(user_id)
  );
  ```
- `CREATE VIEW view_name AS SELECT * FROM orders;`
  - A view is like a virtual table or a saved query.
- `SELECT DISTINCT` retrieves unique tuples of the selected columns
- `UNION`, `EXCEPT`, and `INTERSECT` are used for set operations

# Relational algebra
- SELECT
  - `SELECT *`
  - Symbol: σ
  - `WHERE` is written as a subscript after the symbol
- PROJECT
  - Chooses columns to view (vertical selection)
  - `SELECT ...`
  - Symbol: π
- RENAME
  - `AS`
  - Symbol: ρ
- CARTESIAN PRODUCT
  - Combines the rows of two tables
  - `SELECT * FROM table1, table2 WHERE table1.pk = table2.fk`
  - Symbol: ×

# Advanced SQL
- Don't do `= NULL`, instead use `IS NULL` or `IS NOT NULL`.
- Nested queries
  - Queries can be nested inside the `WHERE` clause
  ```
  SELECT Pnumber
  FROM project
  WHERE Pnumber IN (
    SELECT Pnumber
    FROM project, department, employee
    WHERE Dnum=Dnumber
  );
  ```
  - `ANY()` and `SOME()` can be used to compare a value to multiple values
  ```
  SELECT Lname
  FROM employee
  WHERE Salary > ALL(
    SELECT Salary
    FROM employee
    WHERE Dno=5
  );
  ```
  - `ALL()` and `SOME()` are used to check boolean values. `ALL()` returns true if all elements are true, and `SOME()` returns true if at least one element is true.
  - `EXISTS()` returns true if a nested query is not empty
  ```
  EXISTS(SELECT * FROM dependent WHERE Ssn='0000000000')
  ```
  - `UNIQUE()` returns true if there are no duplicate records
- Aggregation
  - `COUNT`, `SUM`, `MAX`, `MIN`, and `AVG`
- Grouping
  - `GROUP BY` groups rows that have the same values into summary rows.
  - Used with aggregate functions to find stats about the dataset.
  ```
  SELECT COUNT(CustomerID), Country
  FROM Customers
  GROUP BY Country;
  ```
  - `HAVING` filters grouped results, while `WHERE` filters records before grouping.
  - `WITH` creates a temporary table
    - `WITH RECURSIVE` is used for recursive relationships
  - `CASE` is like a swithc statement

# Join
- `INNER JOIN`: Returns records that match in both tables (intersection)
  - Denoted with `⋈`
- Equi-join joins with equality comparisons only
- `NATURAL JOIN` is similar to `INNER` or `LEFT JOIN` except the tables are implicitly joined by columns of similar names
- `LEFT OUTER JOIN` and `RIGHT OUTER JOIN`: Returns all records of one table, and columns of the other tables are null`d.
- Full outer join does not exist in MySQL but can be emulated
  ```
  SELECT * FROM t1
  LEFT JOIN t2 ON t1.id = t2.id
  UNION
  SELECT * FROM t1
  RIGHT JOIN t2 ON t1.id = t2.id
  ```
