[[Build Backend Components]] [[Design the system]]

a hashmap

[[NoSQL]]

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
- Consistency - What you read and write sequentially is what is expected
- Availability - the whole system does not die — every non-failing node always returns a response.
- Partition Tolerant - The system continues to function and uphold its consistency/ availability guarantees in spite of network partitions

BASE - given CAP, best approximation of ACID
- Basically Available — The system always returns a response
- Soft state — The system could change over time, even during times of no input (due to eventual consistency)
- Eventual consistency — In the absence of input, the data will spread to every node sooner or later — thus becoming consistent



Database Index - improve performance of db by 

Structures
* btree - generalizes binary search tree with >2 children nodes
* lsm - log-structured merge tree - good performance for high insert volume
[lsm vs btree]([https://www.linkedin.com/posts/alexxubyte_systemdesign-coding-interviewtips-activity-6988884641034158080-CSq_](https://www.linkedin.com/posts/alexxubyte_systemdesign-coding-interviewtips-activity-6988884641034158080-CSq_))
[8 data structures that power databases](https://www.linkedin.com/posts/alexxubyte_systemdesign-coding-interviewtips-activity-7023329797674037251-0UxN?utm_source=share&utm_medium=member_android)

Vector search database - [milvus](https://milvus.io/)

References
Beginner's Guide to Databases
https://www.linkedin.com/posts/engnadeau_the-beginners-guide-to-databases-activity-7057701348112265217-384u?utm_source=share&utm_medium=member_desktop

[When to Use SQL](https://www.mongodb.com/compare/mongodb-postgresql)

[The Red Book](http://www.redbook.io/) - history of databases


