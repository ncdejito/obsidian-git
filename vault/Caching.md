Why use one global cache?

Antithesis: [Each service should have its own database](https://microservices.io/patterns/data/database-per-service.html) so that

-   Changes to one service’s database does not impact any other services.
-   Each service can use the type of database that is best suited to its needs. E.g. graph/relational

  

[Use global cache](https://youtu.be/U3RkDLtS7uY?t=468) - slower but more resilient to server crashes

Use write through vs write back cache policy - faster with less network calls


Options
Redis
memcached