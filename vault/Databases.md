[[Backend]] [[System Design]] [[Caching]]

## Tools
Dbeaver
Jdbc odbc connectors

## Concepts
ACID - What databases must have/be
- Atomicity - each transaction is treated as a single "unit"
- Consistency - a transaction can only bring the database from one valid state to another
- Isolation - concurrent execution of transactions leaves the database in the same state that would have been obtained if the transactions were executed sequentially
- Durability - once a transaction has been committed, it will remain committed even in the case of a system failure

CAP Theorem - any system cannot be simultaneously all 3
- Consistency - What you read and write sequentially is what is expected (remember the gotcha with the database replication a few paragraphs ago?)
- Availability - the whole system does not die — every non-failing node always returns a response.
- Partition Tolerant - The system continues to function and uphold its consistency/availability guarantees in spite of network partitions

BASE - given CAP, best approximation of ACID
- Basically Available — The system always returns a response
- Soft state — The system could change over time, even during times of no input (due to eventual consistency)
- Eventual consistency — In the absence of input, the data will spread to every node sooner or later — thus becoming consistent

Why NoSQL? (not only SQL)
- Can be much faster than relational
- Developers can structure how data looks like
- Scalable for traffic and zero downtime


References
[When to Use NoSQL](https://www.mongodb.com/nosql-explained/when-to-use-nosql)
[When to Use SQL](https://www.mongodb.com/compare/mongodb-postgresql)

[The Red Book](http://www.redbook.io/) - history of databases