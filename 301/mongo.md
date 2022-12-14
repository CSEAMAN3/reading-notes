# Mongo & Mongoose - Read 11

###### Links

https://aws.amazon.com/nosql/

https://mongoosejs.com/docs/api.html#Model

https://v5.reactrouter.com/web/api/BrowserRouter

https://cloud.google.com/learn/what-is-a-relational-database

https://blog.hubspot.com/marketing/sql-tutorial-introduction

https://www.youtube.com/watch?v=ZS_kXvOeQ5Y

https://www.couchbase.com/resources/why-nosql



### The differences between SQL and NoSQL

###### Point 1

SQL databases are primarily called as Relational Databases (RDBMS).

NoSQL database are primarily called as non-relational or distributed database.

###### Point 2

SQL databases are table based.

NoSQL databases are document based, key-value pairs, graph databases or wide-column stores.

This means that SQL databases represent data in form of tables which consists of n number of rows of data whereas NoSQL databases are the collection of key-value pair, documents, graph databases or wide-column stores which do not have standard schema definitions which it needs to adhered to.

###### Point 3

SQL databases have predefined schema.

NoSQL databases have dynamic schema for unstructured data.

###### Point 4

SQL databases are vertically scalable

NoSQL databases are horizontally scalable.

SQL databases are scaled by increasing the horse-power of the hardware. NoSQL databases are scaled by increasing the databases servers in the pool of resources to reduce the load.

###### Point 5

SQL databases uses SQL ( structured query language ) for defining and manipulating the data, which is very powerful.

NoSQL database, queries are focused on collection of documents. Sometimes it is also called as UnQL (Unstructured Query Language). The syntax of using UnQL varies from database to database.

### What kind of data is a good fit for an SQL database?

SQL databases are good fit for the complex query intensive environment.

### Give a real world example.

### What kind of data is a good fit a NoSQL database?

NoSQL databases are not good fit for complex queries. On a high-level, NoSQL don???t have standard interfaces to perform complex queries, and the queries themselves in NoSQL are not as powerful as SQL query language.

### Give a real world example.

### Which type of database is best for hierarchical data storage?

QL databases are not best fit for hierarchical data storage. But, NoSQL database fits better for the hierarchical data storage as it follows the key-value pair way of storing data similar to JSON data. NoSQL database are highly preferred for large data set (i.e for big data).

### Which type of database is best for scalability?

In most typical situations, SQL databases are vertically scalable. You can manage increasing load by increasing the CPU, RAM, SSD, etc, on a single server. On the other hand, NoSQL databases are horizontally scalable. You can just add few more servers easily in your NoSQL database infrastructure to handle the large traffic.


## Next set of questions

### What does SQL stand for?

Structured Query Langauge

### What is a relational database?

A relational database (RDB) is a way of structuring information in tables, rows, and columns. An RDB has the ability to establish links???or relationships???between information by joining tables, which makes it easy to understand and gain insights about the relationship between various data points. 

### What type of structure does a relational database work with?

data is stored in one or more tables (or "relations") of columns and rows, making it easy to see and understand how different data structures relate to each other. one 2 one, one 2 many, many 2 many.

### What is a ???schema????

A database schema defines how data is organized within a relational database; this is inclusive of logical constraints such as, table names, fields, data types, and the relationships between these entities.


### What is a NoSQL database?

Built to store lots and lots of data.

NoSQL databases store data in documents rather than relational tables. Accordingly, we classify them as ???not only SQL??? and subdivide them by a variety of flexible data models. Types of NoSQL databases include pure document databases, key-value stores, wide-column databases, and graph databases. NoSQL databases are built from the ground up to store and process vast amounts of data at scale and support a growing number of modern businesses.

### How does it work?

NoSQL database technology stores information in JSON documents instead of columns and rows used by relational databases. To be clear, NoSQL stands for ???not only SQL??? rather than ???no SQL??? at all. This means a NoSQL JSON database can store and retrieve data using literally ???no SQL.??? Or you can combine the flexibility of JSON with the power of SQL for the best of both worlds. Consequently, NoSQL databases are built to be flexible, scalable, and capable of rapidly responding to the data management demands of modern businesses. The following defines the four most-popular types of NoSQL database:

###### Document databases 

are primarily built for storing information as documents, including, but not limited to, JSON documents. These systems can also be used for storing XML documents, for example.

###### Key-value stores 

group associated data in collections with records that are identified with unique keys for easy retrieval. Key-value stores have just enough structure to mirror the value of relational databases while still preserving the benefits of NoSQL.

###### Wide-column databases 

use the tabular format of relational databases yet allow a wide variance in how data is named and formatted in each row, even in the same table. Like key-value stores, wide-column databases have some basic structure while also preserving a lot of flexibility

###### Graph databases 

use graph structures to define the relationships between stored data points. Graph databases are useful for identifying patterns in unstructured and semi-structured information.


### What is inside of a Mongo database?

MongoDB stores data records as documents (specifically BSON documents) which are gathered together in collections. A database stores one or more collections of documents.


### Which is more flexible - SQL or MongoDB? and why.

NoSQL databases generally provide flexible schemas that enable faster and more iterative development. The flexible data model makes NoSQL databases ideal for semi-structured and unstructured data.

MongoDB is more flexible and ensures high and diverse data availability, a SQL Database operates with the ACID (Atomicity, Consistency, Isolation, and Durability) properties and ensures greater reliability of transactions.

### What is the disadvantage of a NoSQL database?

May have duplicate data.

If a product name changes for example you may have to udate this in multiple collections.



### NoSQL

Flexibility: NoSQL databases generally provide flexible schemas that enable faster and more iterative development. The flexible data model makes NoSQL databases ideal for semi-structured and unstructured data.

Scalability: NoSQL databases are generally designed to scale out by using distributed clusters of hardware instead of scaling up by adding expensive and robust servers. Some cloud providers handle these operations behind-the-scenes as a fully managed service.

High-performance: NoSQL database are optimized for specific data models and access patterns that enable higher performance than trying to accomplish similar functionality with relational databases.

Highly functional: NoSQL databases provide highly functional APIs and data types that are purpose built for each of their respective data models.

Types of NoSQL databases

###### Key-value: 

Key-value databases are highly partitionable and allow horizontal scaling at scales that other types of databases cannot achieve. Use cases such as gaming, ad tech, and IoT lend themselves particularly well to the key-value data model. Amazon DynamoDB is designed to provide consistent single-digit millisecond latency for any scale of workloads. This consistent performance is a big part of why the Snapchat Stories feature, which includes Snapchat's largest storage write workload, moved to DynamoDB.

###### Document:

In application code, data is represented often as an object or JSON-like document because it is an efficient and intuitive data model for developers. Document databases make it easier for developers to store and query data in a database by using the same document model format that they use in their application code. The flexible, semistructured, and hierarchical nature of documents and document databases allows them to evolve with applications??? needs. The document model works well with catalogs, user profiles, and content management systems where each document is unique and evolves over time. Amazon DocumentDB (with MongoDB compatibility) and MongoDB are popular document databases that provide powerful and intuitive APIs for flexible and iterative development.

###### Graph:

A graph database???s purpose is to make it easy to build and run applications that work with highly connected datasets. Typical use cases for a graph database include social networking, recommendation engines, fraud detection, and knowledge graphs. Amazon Neptune is a fully-managed graph database service. Neptune supports both the Property Graph model and the Resource Description Framework (RDF), providing the choice of two graph APIs: TinkerPop and RDF/SPARQL. Popular graph databases include Neo4j and Giraph.

###### In-memory:

Gaming and ad-tech applications have use cases such as leaderboards, session stores, and real-time analytics that require microsecond response times and can have large spikes in traffic coming at any time. Amazon MemoryDB for Redis is a Redis-compatible, durable, in-memory database service that delivers microsecond read latency, single-digit millisecond write latency, and Multi-AZ durability. MemoryDB is purpose-built to deliver ultra-fast performance and durability so you can use it as your primary database for modern, microservices applications. Amazon ElastiCache is a fully managed, in-memory caching service compatible with both Redis and Memcached, to serve low-latency, high-throughput workloads. Customers like Tinder, who require real-time response from their applications, rely on in-memory data stores rather than disk-based data stores. Amazon DynamoDB Accelerator (DAX) is another example of a purpose-built data store. DAX makes DynamoDB reads an order of magnitude faster.

###### Search: 

Many applications output logs to help developers troubleshoot issues. Amazon OpenSearch Service is purpose-built for providing near-real-time visualizations and analytics of machine-generated data by indexing, aggregating, and searching semistructured logs and metrics. Amazon OpenSearch Service is also a powerful, high-performance search engine for full-text search use cases. Expedia is using more than 150 Amazon OpenSearch Service domains, 30 TB of data, and 30 billion documents for a variety of mission-critical use cases, ranging from operational monitoring and troubleshooting to distributed application stack tracing and pricing optimization.


