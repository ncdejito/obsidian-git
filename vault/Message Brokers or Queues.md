[[Backend]], [[Distributed Systems]]

Why Messaging model (RabbitMQ) for microservice communication?
[Stability for high throughput](https://particular.net/blog/rpc-vs-messaging-which-is-faster)
* If receiver node fails, the message queue can hold the message until the node is ready to receive
* Talking between nodes might be less stable vs having central message queue server that can be distributed

AMQP (RabbitMQ) - for fast transactional messages
DDS (FastDDS in ROS) - for fanning out data across embedded
[Source](https://www.electronicdesign.com/technologies/embedded-revolution/article/21796186/whats-the-difference-between-dds-and-amqp)

  

Remote Procedure Invocation (RPI) vs Messaging
-   RPI - (popular example: REST APIs i.e. put get post) waits for response before moving to the next job. If the job takes too long, memory occupied by the job stays even after the job is done, making the next job slower, creating more memory occupancy.
-   Messaging - producer passes message to an exchange which distributes to consumers ([example diagram](https://www.youtube.com/watch?v=deG25y_r6OY)); benefits: asynchronous, increased availability because exchange passes to consumers only once consumers are available to receive the message
  
“Never depend on synchronous communication (request/response) between multiple microservices, not even for queries. If you think you need to make a call from one microservice to other microservices (like performing an HTTP request for a data query) to be able to provide a response to a client application, you have an architecture that won't be resilient when some microservices fail.” [Communication in Microservices by Microsoft](https://docs.microsoft.com/en-us/dotnet/architecture/microservices/architect-microservice-container-applications/communication-in-microservice-architecture)
