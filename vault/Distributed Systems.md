[[DevOps]] [[System Design]]

## Definitions
Distributed systems - focus on cross-task coordination, communication, synchronization, and failure modes. 
System design - managing the complexity of large bodies of software
Microservices - example of a distributed systems where each component is modelled as a service which can be deployed independently


## Small releases
1. come up with one-line google searches for all unfamiliar terms in zulip thread, log to obsidian distributed systems page
1. do distributed key value store in go via oreilly book
2. github repo Kubernetes the Hard Way on GCP 
3. read codebase for docker
read netflix example - https://github.com/wesen/summer-pasture-netflix/tree/main
message queue - https://github.com/wesen/summer-pasture-netflix/blob/main/message-queue.py
3. [TicTacToe but for many players](https://github.com/recursecenter/wiki/wiki/System-Design)



[Why distributed?](https://microservices.io/patterns/microservices.html)
-   Resilience against high throughput via auto-scaling, self-healing processes
-   Isolatable, smaller integration and deployment procedures with smaller modified components
-   Easy to delegate components to separate teams for autonomous development
-   Take advantage of new emerging technology for each component

Categories
Distributed Data Stores - databases, Cassandra, MongoDB
Distributed computing - Hadoop
Distributed file systems - Hadoop FS
Distributed messaging - activeMQ, rabbitMQ, kafka, amazon sqs
Distributed Applications
Distributed Ledgers - bitcoin ethereum


  
## Factors to consider

1. Reliability - errors of hardware, software, human
1. Scalability - load, performance
1. Maintainability - operability, simplicity, evolvability


Factors not usually taken into account by new distributed programmers: [Fallacies of distributed computing](https://en.wikipedia.org/wiki/Fallacies_of_distributed_computing)

1.  The network is reliable; - spaced out swarm movement to maintain connectivity?
2.  Latency is zero;
3.  Bandwidth is infinite;
4.  The network is secure;
5.  Topology doesn't change;
6.  There is one administrator;
7.  Transport cost is zero;
8.  The network is homogeneous.


 

## Concepts
Race conditions - an undesirable situation that occurs when a device or system attempts to perform two or more operations at the same time (e.g. 5 days Nav2 bug)

Why decompose by business capability?

For cohesive, meaningful distinction
-   [Single Responsibility Principle](https://www.digitalocean.com/community/conceptual_articles/s-o-l-i-d-the-first-five-principles-of-object-oriented-design#single-responsibility-principle) - A class should have one and only one reason to change (i.e. code modified), meaning that a class should have only one job.
-   [Openness for extension and closedness for modification](https://www.digitalocean.com/community/conceptual_articles/s-o-l-i-d-the-first-five-principles-of-object-oriented-design#open-closed-principle) - class should be extendable without modifying the class itself
-   [Common Closure Principle](https://ericbackhage.net/clean-code/the-common-closure-principle/#:~:text=The%20Common%20Closure%20Principle%20(CCP,have%20multiple%20reasons%20to%20change.) - The classes in a component should be closed together against the same kind of changes
-   [Independence in Clean Architecture](https://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html) - independent of frameworks (i.e. unlimited by feature laden packages), testable in isolation, independent of UI (i.e. UI can be changed easily), independent of database (i.e. business rules not bound to database), independent of external agency (i.e. business rules dont know anything at all about the outside world).



Why Tool X for live tracking?
Live tracking - Prometheus, Kibanna, Grafana

  

Why Tool X for api load testing?
Locus test on kubernetes gcp - JMeter, Gatling

  



## Some questions to explore later
Can you use kubernetes and functional programming to have more predictable states?
can I choose not to use ros??


## References
15min intro to distributed systems - https://www.youtube.com/watch?v=k10_trKtKNk
distributed systems from the ground up! (Go) https://www.oreilly.com/library/view/cloud-native-go/9781492076322/
distributed services with go - https://pragprog.com/titles/tjgo/distributed-services-with-go/
patterns in distributed systems - https://martinfowler.com/articles/patterns-of-distributed-systems/
Patterns of Enterprise Applications - https://martinfowler.com/books/eaa.html
Raft consensus algorithm with viz - https://raft.github.io/

Designing Data Intensive Applications - Martin Kleppmann
[Mastering Chaos - A Netflix Guide to Microservices](https://www.youtube.com/watch?v=CZ3wIuvmHeM)
[Introduction to Microservices, Docker, and Kubernetes](https://www.youtube.com/watch?v=1xo-0gCVhTU) - James Quigley 
[MIT 6.824](https://www.youtube.com/playlist?list=PLrw6a1wE39_tb2fErI4-WkMbsvGQk9_UB)
[DockerSwarm vs Kubernetes](https://circleci.com/blog/docker-swarm-vs-kubernetes/)
[Thorough Introduction to Distributed Systems](https://www.freecodecamp.org/news/a-thorough-introduction-to-distributed-systems-3b91562c9b3c/)
Paper on [Software Technologies for Developing Distributed Systems: Objects and Beyond ](https://www.dre.vanderbilt.edu/~schmidt/PDF/CSI-article.pdf)

Topics in distributed systems https://youtu.be/BkSdD5VtyRM

Existing Tech
Docker Swarm - is a lightweight, easy-to-use orchestration tool with limited offerings compared to Kubernetes
Kubernetes - is complex but powerful and provides self-healing, auto-scaling capabilities out of the box
