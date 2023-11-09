## C++
https://github.com/vpetrigo/caches
LRU https://leetcode.com/problems/lru-cache/solutions/3171305/solution/


## System design
Why
* enables faster content delivery 
* reduces main server network traffic

Why use one global cache?

Antithesis: [Each service should have its own database](https://microservices.io/patterns/data/database-per-service.html) so that

-   Changes to one service’s database does not impact any other services.
-   Each service can use the type of database that is best suited to its needs. E.g. graph/relational

  

[Use global cache](https://youtu.be/U3RkDLtS7uY?t=468) - slower but more resilient to server crashes

Use write through vs write back cache policy
* write through - When data is updated, it is written to both the cache and the back-end storage
* write back - When data is updated, it is written only to the cache; faster with less network calls


Options
Redis - often utilized as a primary database or a message broker and offers a clear growth path to an enterprise-hardened solution
memcached - cache-focused key/value store