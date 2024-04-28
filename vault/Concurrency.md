[[Distributed systems]]

Goal: Prevent Race conditions i.e. program behavior differs based on which statement ran first, ran first out of random chance

Solutions: Synchronize processes with semaphores
Mutexes - a binary semaphore ex. m.Lock critical section m.Unlock
Semaphores - counting semaphore ex. Give(2) Take(1)

Async
Await
Promises
Futures
