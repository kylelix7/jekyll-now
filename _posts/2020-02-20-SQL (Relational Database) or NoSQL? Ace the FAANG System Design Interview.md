---
layout: post
title: SQL (Relational Database) or NoSQL? Ace the FAANG System Design Interview
tags: SQL, NoSQL, System Design Interview, FAANG, Job
---

![header](https://miro.medium.com/max/7912/0*hod3Y0N8D8dtPEav)
Photo by Taylor Vick on Unsplash


Many systems require permanent data store to store application data. With the rise of NoSQL databases in these years, it is critical to identify to different strengths of SQL and NoSQL databases, and pick the right database that fit your use case. When it comes to technical system design interview in those big tech companies, being able to compare the tradeoff of SQL and NoSQL can be a good indicator of a competent candidate.


# Schemaless

The key difference, of course, is the structure of the data. As you know, in the world of relational database, data is stored in a table. And each row of a table has the same set of columns. That means the data model is well modeled. In contrast, NoSQL database offers very flexible data model. Data is stored as documents or items. Each item can have different columns. For example, in AWS DynamoDB, you can define a table with a partition key and sort key. The rest of attributes are inserted/updated during runtime in a relaxed manner.

# Consistency

Relational Database is [ACID](https://en.wikipedia.org/wiki/ACID) (Atomicity, Consistency, Isolation, Durability) compilance. Those SQL databases are strong consistency. While may NoSQL provides very high performance at the cost of consistency. Most NoSQL only offer eventual consistency, or some support strong consistency but offer eventual consistency as default.

# Vertical Scalablity vs Horizontal Scalability

Cost of scaling SQL database horizontally is very high due to the complexity of managing ACID compilance in massive number of nodes. Hence, most SQL databases scale vertically. That means it requires to upgrade hardware for a single node. That kind of scalabity is much higher comparing to horizontal scalability. Horizontal scalability relies on many low-cost commodity computers to perform intense workload. Most NoSQL can expand horizontally to get better performance without/with very little nodes management cost. NoSQL database can handle more requests by routing them to different shards.

# Query

SQL database has standard query language. In contrast, the NoSQL databases have its own query language. So migrating a SQL database from one vendor to another vendor may not need to change anything at the application level. While changing NoSQL database from one to another may requires some code changes.

# Last words

There are definitely more topics for you to dive deep if you’re interested in database. [ACID](https://en.wikipedia.org/wiki/ACID) and [CAP Theorem](https://en.wikipedia.org/wiki/CAP_theorem) are great topics to learn about. Understanding the basics and being able to read the user guide from database vendor are critical skills when you choose your database.

