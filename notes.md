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
- Relational model
  - Based on mathematical models to abstract the storage details
- Object-oriented
  - Not common today
- NOSQL
  - Unstructured data with flexible models of tx processing

# When not to use a DBMS
- Overhead costs such as for maintenance and training
- Real-time or embedded applications