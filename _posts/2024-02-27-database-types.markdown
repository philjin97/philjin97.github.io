---
layout: post
title: Understanding Database Types and When to Use Them
image: 11.jpg
date: 2024-02-27 22:00:00 +0200
tags: [database]
categories: database
---
Understanding what types of database exist and when to use them can help us make wiser decisions when we choose what database system to use for our application. 

Types of Databases: Relational, Columnar, Document, Graph, Vector, Key-value 

RDBMS (Relational Database) 

Structured data - You have rows and columns that clearly define data attributes. 
,  ACID compliance

MySQL, Maria DB, PostgreSQL, Amazon Aurora, Azure SQL 

Traditional databases don’t scale very well. With more data, performance drops. 
In order to improve query performance, NoSQL (Columnar database) developed. 

1. Read the data from left to right
2. Proceed from row to row 

Columnar database

1. Read data from top to bottom
2. Read only columns that are required

When viewing the items from each row of data, assign a number to each row of data allowing the data to be paired with the same rows. 
Columnar database does not read billions of rows of data and reads a few long columns. 

Apache Cassandra

Document database

Different products have different characteristics, and managing thousands of characteristics that only have some products correspond to certain characteristics can be inefficient. This is where document databases come in. Even if you change the attribute of one, it doesn’t affect the entire database. 

Uses json. 

Json documents structure
1. Key value
2. Array 
3. Objects 

Flexible schema. 
Can create, read, update, and delete entire documents. 

Advantage
1. Ease of development. No need to create a data model.
2. Flexible schema. Documents with different fields. 
3. Performance at scale. Built-in distribution capabilities and can scale them horizontally. 

MongoDB


Graph database 

Relational database - constrains nature of its relationships. Makes it hard to answer questions about distant relationships. 

Graphs have nodes - which are records. Connected to the nodes are the relations which can have a direction and a property. 
Querying - own querying language. However, have to be careful as they might show meaningless relationships. Graph databases are usually a mechanism for starting questions but not necessarily answering them. Graph databases are used to test inferences. 

ArangoDB


Vector database

Store data as vectors. Even if it is unstructured data or structured data, transform through embedding model to a vector that captures context and meaning of the asset. Can allow us to find similar assets by searching for neighboring data points. 

Milvus 

Key-value database 

Stores data as key-value pairs. Both keys and values can be anything. 
Vs. Document database (document databases keys can only be strings, and you can read entire value or a part of the value). 

Advantages 
1. Scalability. Scale horizontally and distribute data across servers 
2. Ease of use
3. Performance 

Use cases
1. Session management 
2. Shopping cart 
3. Metadata storage engine 
4. Caching 

Etcd 

Time-series database 

Optimized for time-stamped data. Measurements or events that are tracked, monitored, downsampled, and aggregated over time. Examples are server metrics, application monitoring, network data, sensor data, events, clicks, trades in a market. 

Advantage
1. Fast data retrieval 
2. Cost effective 

InfluxDB, Prometheus



Situation: 
Relational: structured data and ACID compliance
Columnar: analytics 
Document: unstructured data 
Graph: complex relationships
Time-Series: time-stamped data 
Vector: AI and ML scenarios 
Key-Value: simple, fast data access  