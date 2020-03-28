---
layout: post
title: Steps to Ace the FAANG System Design Interview
tags: FAANG, System Design Interview, Interview, Job
---

![header](https://miro.medium.com/max/1400/0*QjEv1GdiUIcWnJQK)
Photo by Johanna Buguet on Unsplash


# Clarification

System design interviews, like coding interviews, do not only test candidates’ technical skills, but also validate if candidates can solve a problem that’s not well defined. Questions are asked vaguely and generally. It’s candidates’ job to find out the requirements and come up with a proper design. It’s a common mistake for a candidate to jump into design right after the get the question. For a question like design at Twitter, you may need to find out what core features are needed to consider, registration? profile? text tweet? video/image tweet? Timeline? Other technical requirements may be Read or write per second? Peak/Avg number of requests? Users base location?

# Key components for working solution

Once you have the requirements, you can start to think about the structure of the system or its subsystems if it’s for more than one feature. It’s always good to find out a working solution first instead of trying to come up with a perfect optimal solution. Try to come up with a simple system with all necessary components. Lay out the system on the whiteboard. Components are like Application Servers, Data store (SQL or NoSQL), Proxy, CDN, Message Queue, Event Bus etc. Pick the components the basic solution needs. Explain why these components are required, how they should be connected together, and how users interact with the systems.

# List the APIs

APIs are expression of communication between components. Being able to design a set of logic APIs is a plus for candidate. For RESTful API, it’s good to follow REST convention to use HTTP verbs proper for resource operation like CRUD. Paths should be nouns that represent resources. It’s also helpful to show that you can use query parameters, request body properly in your design.

# Optimization

Then, you need to optimize the system. When considering optimization, you will need to optimize the right thing. It’s better to optimize for common use cases. For example, if it’s more common to read data from a database than to write data to the database, it makes sense to introduce a cache between the data requester and the persistent data store. It helps serve hot data much more quickly, and cache invalidation will be less frequent as write isn’t a lot. But introducing a cache for a write intense system would have a negative impact on performance because it will frequently cause cache invalidation. Other optimization could be distributing requests to different datacenters base on users’ location. Partition the database into shards to handle requests. Properly design keys in the table so that request traffic will be evenly distributed to the partition.

# Scalability

How about as your user base grows? It is always certain that you will need to design a horizontally scalable system. Horizontal scalability means that the system can handle more requests by adding more and more commodity computing power. It’s more cost-effective than adding more horsepower to one single server.

# Tradeoff

There’s no doubt that you have heard of a lot of popular software to build a distributed system. Things like MongoDB, ElasticSearch, Memcached, Kafka etc. However, randomly throw these buzzwords to the interviewers won’t be enough to impress them. It is critical for you to explain the choice and why not to choose the other. For example, what benefits does MongoDB give you that MySQL won’t? Maybe your application doesn’t care about the relation between data model and would prefer better performance over strong consistency. For another example, why you will prefer to build event-driven system with Kafka. Maybe your business logic is long process and it needs to complete it asynchronously. Maybe you have a few subsystems that need to know of the event.

# Error handling

Software is never perfect, so you as a candidate should explain how your system handles errors. One key point is that you are able to identify a single point of failure and provide a solution to lower the chase of failing the entire system. Another common error scenario is that the traffic is too large for the system to handle. One common solution is throttle. Throttling is the process of limiting the number of requests to the system. By limiting number of requests per client, the system can have relatively predictable workload. Hence, it also helps to plan scalability.

# Last words

These are some points that you would like to consider during the system design interview. If you would like to get more technical details about the system design, I would recommend use Designing Data-Intensive Applications as reference for the preparation. Good Luck.
