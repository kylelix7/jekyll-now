---
layout: post
title: Ace the System Design Interview in FAANG
tags: Career, Interview, Job Hunting, FANG Job, IT jobs, System Design
---

![header](https://miro.medium.com/max/5472/0*JDJ47S42LYReZ7kr)
(Photo by [Andy Kelly](https://unsplash.com/@isaacmsmith?utm_source=medium&utm_medium=referral) on Unsplash)


System design is common in technical interview these days. If coding interview validate the ability to code, then system design interview validates the ability to build. It verifies whether a candidate can build a system that can perform at scale and tolerrant faluts. There are so many great resources, like [Groking System Design](https://www.educative.io/courses/grokking-the-system-design-interview) or [Designing Data-Intensive Applications](https://www.amazon.com/gp/product/1449373321/ref=as_li_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=1449373321&linkCode=as2&tag=blog023b-20&linkId=c2a54da05c554be38ae17a0a7c1a0046) which give you great examples and details about the best practice for system design. But after I talked to many people, I feel many of them tend to memorize the solutions for each example. Hence, I find writting down summary about these rules of thumbs is critical for you to react in a real interview. Here is my summary.


# Cache
What problem does cache solve?


Access to persistant storage, like hard disk is slow. In applications that need to frequently read from database or file, the performance bottleneck usually comes from the access speed to disk. Hence, we tend to add high frequently accessed data in memory, because access to memory is way faster.


What’s the limitation?

Memory usually isn’t large enough to hold the entire dataset. So, application developers will need to selectively save subset of data in cache
Memory is lost if it lost power


When should you NOT use cache?

Don’t use it if the data is write heavy, because if you need consistent result, cache will be invalidated in every write operation. That makes the performance even worse?


# Batch write

What happen if the application is write heavy?


We know how to mitigate the read for adding cache between application and persistent storage. For write, we can batch the write operations, and do it in one shot. For example, we can keep track of all write operations in memory, and apply them all when there are 100 writes happen.


The tradeoff is that the read won’t be consistent. It is possible that a read immediately following a write can’t get the most recent update.

# Sharding

What’s sharding?


It essentially breaks the data into different paritions. This help scale up the database across different machines to improve scalability, performance, availability etc.

# Availablity / Redundency
When designing a system, it’s common to replicate each components like app server, database etc. This makes sure there’s no single point of failure. It greatly increase the availabity by adding redundency.

# Load balancer
We introduce redudent component to avoid single point of failure. In the same time, multiple machines can share the loads of request. How should we distribute the requests to different servers? This is a load balancer’s responsibility. It typically sits between a client and servers. It routes the request from client to a server to make sure all servers have same amount of load. There are many algorithms that can be used in load balancer, e.g. round robin, least connection method, least response time method etc.

# SQL vs. NoSQL
SQL and NoSQL databases are very different in the way how data is stored. In SQL data models are relational, meaning all rows have the same column/attributes. Whereas NoSQL has very flexible schema. Each document can have different attributes.


There’s another big difference about consistency. SQL support strong consistency. That means all database nodes have the same copy of data at the same time, while NoSQL mostly support eventual consistency. That means a write to database nodes is async. It doesn’t guarantee to have all nodes to have the same data at a given time. But eventually, all nodes will have all write update. This also make NoSQL more efficient in many scenario.


There are more in-depth details in SQL vs. NoSQL and CAP Therem in Groking System Design.


In the end, I hope this summary can help you get ideas about building systems in both interview and at work.

