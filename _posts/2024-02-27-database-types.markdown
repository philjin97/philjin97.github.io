---
layout: post
title: Understanding Database Types and When to Use Them
image: 11.jpg
date: 2024-02-27 22:00:00 +0200
tags: [database]
categories: database
---
### Understanding what types of database exist and when to use them can help us make wiser decisions when we choose what database system to use for our application. 

### 6 Types of Databases: Relational, Columnar, Document, Graph, Vector, Key-value 

Relational: structured data and ACID compliance
Columnar: analytics 
Document: unstructured data 
Graph: complex relationships
Time-Series: time-stamped data 
Vector: AI and ML scenarios 
Key-Value: simple, fast data access  

***

### RDBMS (Relational Database) 

RDBMS is useful when dealing with structured data that have rows and columns that clearly define data attributes and have ACID compliance. 

ACID - Atomicity, Consistency, Isolation, Durability

RDBMS doesn’t scale very well. This means that with more data, query performance drops. 
Why? When querying data, RDBMS reads the data from left to right and proceeds from row to row. Thus, when you search for values on a single column in a table, you need to go through all the columns and rows which takes much more time. 

Examples: MySQL, Maria DB, PostgreSQL, Amazon Aurora, Azure SQL 

***

### Columnar Database

Columnar databases have higher query performance compared to RDBMS.  
Why? When querying data, Columnar databases read the data from top to bottom and only the columns that are required. This means that Columnar databases do not read billions of rows of data but only reads a few long columns. 

How does the data collected get organized again? The data collected each are assign a number to each row of data allowing the data to be paired with the same rows. 

Example: Apache Cassandra

***

### Document Database

Different products have different characteristics, and managing thousands of characteristics that only have some products correspond to certain characteristics can be inefficient. This is where document databases come in. Even if you change the attribute of one, it doesn’t affect the entire database. 

Document databases uses Json and follows the Json document structure.
1. Key value
2. Array 
3. Objects 

Flexible schema. 
Can create, read, update, and delete entire documents. 

Advantage
1. Ease of development. No need to create a data model.
2. Flexible schema. Documents with different fields. 
3. Performance at scale. Built-in distribution capabilities and can scale them horizontally. 

Example: MongoDB

***

### Graph Database 

How does it solve RDBMS problems?
Relational database has a constrained nature of its relationships. This makes it hard to answer questions about distant relationships. Here is where the Graph database comes in. Graph databases have nodes which are records. Between the nodes are relations that have a direction and a property. This allows querying for relationships much easier. 

However, you have to be careful as they might show meaningless relationships. Thus, Graph databases are usually a mechanism for starting questions but not necessarily answering them. Graph databases are used to test inferences. 

Example: ArangoDB

***

### Vector Database

Vector databases store data as vectors. Whether it is structured data or unstructured data, vector databases transform the data through an embedding model to a vector that captures context and meaning of the asset. This allows us to find similar assets by searching for neighboring data points. 

Example: Milvus 

***

### Key-value database 

Key-value databases store data as key-value pairs. 

How are key-value databases different from document databases?
Document databases only allow the keys to be strings. Moreover, you can query the value for the entire value or a part of the value. 
However, with key-value databases, the keys can be integers and you always get the entire value. 

Advantages 
1. Scalability. Scale horizontally and distribute data across servers 
2. Ease of use
3. Performance 

Use cases
1. Session management 
2. Shopping cart 
3. Metadata storage engine 
4. Caching 

Example: etcd 

***

### Time-series database 

Time-series database is optimized for time-stamped data. Measurements or events that are tracked, monitored, downsampled, and aggregated over time. Examples are server metrics, application monitoring, network data, sensor data, events, clicks, trades in a market. 

Advantages
1. Fast data retrieval 
2. Cost effective 

Examples: InfluxDB, Prometheus

***