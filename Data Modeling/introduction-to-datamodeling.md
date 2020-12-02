# Data Modeling

## What is data modeling?
- An abstract model for information systems
- Organize data into a database system to ensire that data is presistent and usable
- Supports business and application
- Steps:
    - Process to support business and user application
    - Gather requirements
    - Conceptual data modeling
    - Logical data modeling
    - Physical data modeling (ddl)

## Why is data modeling important?
- Key points
    - Data Organization: The organization of the data for your applications is extremely important and makes everyone's life easier.
    - Use cases: Having a well thought out and organized data model is critical to how that data can later be used.
    - Starting early: Thinking and planning ahead will help you be successful.
    - Iterative Process: Data modeling is not a fixed process. It is iterative as new requirements and data are introduced.
  
## Intro to Relational Databases
-   Organizes data into one or more tables of columns and rows with an unique key identifying each row. Generally, each table represents an entity.
-   The basics
    -   A database, or in some database is called schema, is a collection of tables
    -   A table or a relation is a group of row sharing the same labeled element or columns

## When to use a relational database
- Advantages
    -  Ease of use of SQL
    -  Joins
    -  Agg and analytics
    -  Smaller data volumes
    -  Easier to change business requirements
    -  Flexible queries
    -  Model the data not the queries
    -  Secondary indexes
    -  ACID txs


## ACID transactions
- ACID properties:
    - ACID intends to guarantee validity even in the event of errors
    - Atomicity: The whole transaction is processed or nothing is processed.
    - Consistency: Only transactions that abide by constraints and rules are written into the database, otherwise the database keeps the previous state.
    - Isolation: Transactions are processed independently and securely, order does not matter.
    - Durability: Completed transactions are saved to database even in cases of system failure.

## When not to use a relational database
- Have large amounts of data: Relational Databases are not distributed databases and because of this they can only scale vertically by adding more storage in the machine itself.
- Need to be able to store different data type formats
- Need high throughput -- fast reads: While ACID transactions bring benefits, they also slow down the process of reading and writing data. If you need very fast reads and writes, using a relational database may not suit your needs.
- Need a flexible schema: Flexible schema can allow for columns to be added that do not have to be used by every row, saving disk space.
- Need high availability: The fact that relational databases are not distributed (and even when they are, they have a coordinator/worker architecture), they have a single point of failure.
- Need horizontal scalability: Horizontal scalability is the ability to add more machines or nodes to a system to increase performance and space for data.

## NoSQL databases
- Not only SQL
- Various types of databases
- Types:
    - Apache Cassandra (partition row store)
    - MongoDB (document store)
    - DynamoDB (key-value store)
    - Apache HBase (wide column store)
    - Neo4j (graph database)
- Apache Cassandra:
    - keyspace:
        - collection of tables
    - table:
        - a group of partitions
    - row:
        - a single item
    - partition:
        - fundemental unit of access
        - collection of rows
        - how data is distributed
    - primary key
        - partition key and clustering columns
    - columns
        - clustering data
        - labeled element