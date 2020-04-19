---
layout: post
title: System Design Interview Prep - Should You Put the Data in Cache?
tags: FAANG, System Design Interview, Interview, Job
---

Cache is a data store that serves data at a relatively fast speed. There are hardware and software caches. In system design interview, we will focus on software cache mostly. In many cases, cache are blocks of memory that store data. Since the speed of accessing memory is much faster than IO like disk and network, applications can put the data in memory to avoid accessing IO. As a result, throughput can be increased and latency can be decreased.


# Not all data fits in cache

Cache is stored in memory, and it is usually much smaller than a persistent store, like a disk. So, it is not practical to store everything in the cache if your application needs to deal with a large volume of data. Only a small subset of data should be placed in cache. When the data can be found in the cache, it’s called cache hit. If not, it’s called cache miss.


It is critical for the system designer to find out what data needs to be in cache. It’s not hard to find out, only hot data which is requested frequently should stay in cache. For the example of designing a Facebook, posts must be hotter than user profiles. And those posts from celebrities must be much hotter than those regular users. So, you should prioritize this in the interview.


# Not all applications should have cache

It is important to know that cache does not increase throughput in all kinds of systems. In some cases, it has a negative impact on the system. For example, if your system needs to update or write data frequently, data in cache would need to be constantly changing too. That results in a cache massive invalidation. Therefore, the application needs to mark the data in cache as invalid. Also, it will need to write the updated data to its corresponding persistent data store. In this example, the invalidation of cache becomes an overhead. So cache is beneficial to only those applications that is read-heavy but not write-heavy.

# Cache Writing Policies


When an application needs to update the data, it will need to:

1. update data in the persistent data store.
2. invalidate or update the data in the cache. There a few types of cache writing policies.


*Write-through*: write the new data to cache and backing data store synchronously.

The advantage is that the data is consistent on both backing and cache. Update to the data won’t be lost if there’s power outage.

*Write-back*: write to cache first. It will not write to the backing data store until the data is replaced.


The advantage is that write is faster because there is no need to update backing data store.


The disadvantage is that it can potentially lose update. Also, the implementation is more complex, since it needs to keep track of which cache block is updated in the cache, but not yet written to disk. This type of cache block is called dirty.


The disadvantage is that the time that spent on the write is much longer since it does not need to write to a persistent data store which is very slow.

# Cache Replacement Policies


Because the cache is small and meant to hold only a small subset of hot data, it can run out of its limit. In this scenario, when a new request comes, and there’s cache miss, we will need to evict a block for the new data. This process is call replacement. There are many algorithms for cache replacements to find which piece of cache to evict. The best policy depends on what an application does. I will introduce two famous policies here.


*Least Recently Used*, LRU, it discards the least recently used data. In this policy, the “when” needs to be tracked.


*Least Frequently Used*, LFU, it discards the data that is used least frequently. The count of usage is tracked.

# Summary


Cache is a way to optimize read-heavy application. It increases throughput and decreases latency by putting a relatively small amount of hot data in the memory so that data access can avoid hitting the disk. Depending on your application, you may want to choose write policy and cache replacement policy accordingly for best performance. To learn more about System Design, you can find more in [Designing Data-Intensive Applications](https://www.amazon.com/gp/product/1449373321/ref=as_li_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=1449373321&linkCode=as2&tag=blog023b-20&linkId=c2a54da05c554be38ae17a0a7c1a0046) and [Groking System Design](https://www.educative.io/courses/grokking-the-system-design-interview?aff=VEzk).

