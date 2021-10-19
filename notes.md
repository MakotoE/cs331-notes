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
- Shapes
  - Rectangle = Entity
  - Double rectangle = Weak entity (Cannot be identified by its attributes alone)
  - Oval = Attribute
  - Double oval = Multivalued attribute
  - Diamond = Relationship (Connects two strong entities)
  - Double diamond = Identifying relationship (Connects a weak entity)
  - Line = Partial participation (Not all entities are involved in the relationship)
  - Double line = Total participation (All entities are involved in the relationship)

# Enhanced Entity-Relationship Modeling
- A subclass is denoted with a line originating from the superclass, passing through a circled "d" or "o", depending on the constraint, and connecting to the subclass. There is a symbol "U" on the line pointing toward the subclass.
- A local attribute, which is an attribute for only the subclass, may be connected to the subclass
- Specialization constraint
  - Disjoint constraint
    - An entity can only be a member of one subclass only for a given specialization
    - Uses a "d" symbol
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
- Union type: A class that can represent different subclasses (Just like C unions)