# Relational data mdoels
---
## Importance of relational databases
- The information rule: All information in a relational database is represented in exactly one way at the logical level - by values in tables
- Relational importance
    - Standarization of data model
    - Flexibility in adding tables and altering them
    - Data integrity
    - SQL
    - Simplicity
    - Intuitive organization

## OLAP & OLTP
- OLAP:
    - Complex analytics and ad hoc queries
- OLTP:
    - Less complex queries in large volume

## Structuring the database
- Normalization: To reduce data redundancy and increase data integrity. Proposed by Edgar Codd
- Denormalization: Must be done in read heavy workloads to increaase performance


## Objectives of normal form
- Free the database from unwanted insertions, updates, and deletion dependencies
- Reduce the need of refactoring the database when a new data types is added
- Make the model more informative
- Database neutral to query statistics

## Normal forms
- The normal forms:
    - First normal form (1NF)
    - Second normal form (2NF)
    - Third normal form (3NF)
- 1NF
    - Atomic values: each cell contains unique and single values
    - Be able to add data without altering tables
    - Separate different relations into different tables
    - Keep relationships between tables together with foreign keys
- 2NF
    - Have reached 1NF
    - All columns in the table must rely on the Primary Key
- 3NF
    - Must be in 2nd Normal Form
    - No transitive dependencies
    - Remember, transitive dependencies you are trying to maintain is that to get from A-> C, you want to avoid going through B.

## Fact and Dimension tables
- A dimension is a structure that categorizes facts and measures in order to enable users to answer business questions.
- In data warehousing, a fact table consists of the measurements, metrics or facts of a business process. It is located at the center of a star schema or a snowflake schema surrounded by dimension tables.

## Star Schemas
- A fact table surrounded by dimensional tables.
- The star schema is the simplest style of data mart schema and is the approach most widely used to develop data warehouses and dimensional data marts.[1] The star schema consists of one or more fact tables referencing any number of dimension tables. The star schema is an important special case of the snowflake schema, and is more effective for handling simpler queries.

## Benefits of Star Schemas
- Benefits:
    - Denormilized
    - Simplifies queries
    - Fast aggregations
- Drawbacks:
    - Issues come with denormalization
    - Data integrity
    - Descreases query flexibility
    - Many to many relationships -- simplifed

## Snowflake Schemas
- Logical arrangement of tables in a multidimensional database represented by centralized fact tables which are connected to multiple dimensinons
- Star schemas are a simplified version of snowflake

## Data definition and constraints
- not null
- unique
- primary key

## Upsert
- In RDBMS language, the term upsert refers to the idea of inserting a new row in an existing table, or updating the row if it already exists in the table. The action of updating or inserting has been described as "upsert".
- The way this is handled in PostgreSQL is by using the INSERT statement in combination with the ON CONFLICT clause.
- INSERT INTO customer_address (customer_id, customer_street) VALUES ( 432, '923 Knox Street, Suite 1') ON CONFLICT (customer_id) DO UPDATE SET customer_street = EXCLUDED.customer_street;
- INSERT INTO customer_address (customer_id, customer_street) VALUES (432, '923 Knox Street, Suite 1') ON CONFLICT (customer_id) DO UPDATE SET customer_street  = EXCLUDED.customer_street;