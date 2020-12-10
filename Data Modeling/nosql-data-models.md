
# NoSQL Data Models
---

## Non Relational Databases
- NoSQL and non relational are interchangeable
- When to not to use SQL
    - Need high Availability in the data: Indicates the system is always up and there is no downtime
    - Have Large Amounts of Data
    - Need Linear Scalability: The need to add more nodes to the system so performance will increase linearly
    - Low Latency: Shorter delay before the data is transferred once the instruction for the transfer has been received.
    - Need fast reads and write
- [https://www.xenonstack.com/blog/nosql-databases/] (No SQL Databases)
## Distributed Database
- Database scaled horizontaly
- High availability: Low down time
- Needs copy of data, eventual consistency. Eventually all accessses of that item will return the last updated value.

## CAP Theorem
- It is impossible to simoultaneously provide more than two out of three: consistency , availabilty and partition tolerance
- Apache Cassandra is an AP database availabilty and partition tolerance
- [https://www.voltdb.com/blog/2015/10/disambiguating-acid-cap/] (Discussion)

## Denormalization in Apache Cassandra
- Denormalization must be done for fast reads.
- Apache Cassandra has been optimized for fast writes
- Think in queries first
- One table per query
- There are no JOINS in Apache Cassandra
  
## Primary Key
- Must be unique
- The PRIMARY KEY is made up of either just the PARTITION KEY or may also include additional CLUSTERING COLUMNS
- A Simple PRIMARY KEY is just one column that is also the PARTITION KEY. A Composite PRIMARY KEY is made up of more than one column and will assist in creating a unique value and in your retrieval queries
- The PARTITION KEY will determine the distribution of data across the system