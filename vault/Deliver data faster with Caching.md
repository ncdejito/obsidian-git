## C++
https://github.com/vpetrigo/caches
LRU https://leetcode.com/problems/lru-cache/solutions/3171305/solution/

Edge cases/Ways cache systems can go wrong
https://www.linkedin.com/posts/bytebytego_systemdesign-coding-interviewtips-activity-7238422879611023360-ChEh?utm_source=share&utm_medium=member_android

## System design
Why
* enables faster content delivery 
* reduces main server network traffic

Why use one global cache?

Antithesis: [Each service should have its own database](https://microservices.io/patterns/data/database-per-service.html) so that

-   Changes to one service’s database does not impact any other services.
-   Each service can use the type of database that is best suited to its needs. E.g. graph/relational

  
## glossary
[Use global cache](https://youtu.be/U3RkDLtS7uY?t=468) - slower but more resilient to server crashes

Use write through vs write back cache policy
* write through - When data is updated, it is written to both the cache and the back-end storage
* write back - When data is updated, it is written only to the cache; faster with less network calls

Cache hits - a request from the cache where the request is fulfillable using the contents of the cache
cache miss - the data point does not exist in the cache

Options
Redis - often utilized as a primary database or a message broker and offers a clear growth path to an enterprise-hardened solution
memcached - cache-focused key/value store

Considerations
https://www.linkedin.com/posts/bytebytego_systemdesign-coding-interviewtips-activity-7293885383551954944-uktg?utm_source=share&utm_medium=member_android