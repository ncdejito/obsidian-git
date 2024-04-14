Scale
- [[Connect robot to the cloud]]
- [[Build network infrastructure]]
* [[Measure]]

System design 101 visuals
https://email.changelog.com/t/t-l-vduihjd-wjuliuuyk-ut/

Design process from research
https://maheshba.bitbucket.io/blog/2023/07/12/Design.html

Scalable systems  
[https://www.linkedin.com/posts/garrytan_how-we-reduced-the-cost-of-building-twitter-activity-7097287204028239872-nBqn?utm_source=share&utm_medium=member_android](https://www.linkedin.com/posts/garrytan_how-we-reduced-the-cost-of-building-twitter-activity-7097287204028239872-nBqn?utm_source=share&utm_medium=member_android)
System design blogs  
[https://www.linkedin.com/posts/ashishps1_40-blogs-to-build-a-strong-system-design-activity-7148169873565569026-T4ys?utm_source=share&utm_medium=member_android](https://www.linkedin.com/posts/ashishps1_40-blogs-to-build-a-strong-system-design-activity-7148169873565569026-T4ys?utm_source=share&utm_medium=member_android)

Design a system using AI
https://github.com/geekan/MetaGPT

SHDW - from System Design Interview
Scope needs
High level design
Deep-dive
Wrap up

Plan
Identify system needs in metrics
* [[Make it Resilient]] - kill one vm, data is safe
* [[Make it Scalable]] - 50 daily
* [[Make it Maintainable]] - crisp abstractions, interfaces, inviting quickstarts
* [[Make it Observable]] - order status dashboard
* [[Make it Cost-aware]] - set budget, auto kill
[[Find usable design patterns]]
[[Find usable existing components]]
[[Compare technology tradeoffs]]

Execute
Trace flow of 1 small data example
Do quickstarts after [[Find usable existing components]]
[[Program asynchronously]]
[[Connect computers with Networking]]

[[Keep in mind programming principles]]
[[Avoid common mistakes in distributed]]
[[Document code]]


## Example systems
[Twitter System from Elon](https://www.linkedin.com/posts/eric-vyacheslav-156273169_elon-just-tweeted-the-whole-twitter-back-end-activity-6999730758609170432-w-fB?utm_source=share&utm_medium=member_desktop)
Categories
Distributed Data Stores - databases, Cassandra, MongoDB
Distributed computing - Hadoop
Distributed file systems - Hadoop FS
Distributed messaging - activeMQ, rabbitMQ, kafka, amazon sqs
Distributed Applications
Distributed Ledgers - bitcoin ethereum

## Definitions
Distributed systems - focus on cross-task coordination, communication, synchronization, and failure modes. 
System design - managing the complexity of large bodies of software
Microservices - example of a distributed systems where each component is modelled as a service which can be deployed independently
Race conditions - an undesirable situation that occurs when a device or system attempts to perform two or more operations at the same time (e.g. 5 days Nav2 bug)

[Why distributed?](https://microservices.io/patterns/microservices.html)
-   Resilience against high throughput via auto-scaling, self-healing processes
-   Isolatable, smaller integration and deployment procedures with smaller modified components
-   Easy to delegate components to separate teams for autonomous development
-   Take advantage of new emerging technology for each component


## Practice
1. come up with one-line google searches for all unfamiliar terms in zulip thread, log to obsidian distributed systems page
1. do distributed key value store in go via oreilly book
2. github repo Kubernetes the Hard Way on GCP 
3. read codebase for docker
read netflix example - https://github.com/wesen/summer-pasture-netflix/tree/main
message queue - https://github.com/wesen/summer-pasture-netflix/blob/main/message-queue.py
3. [TicTacToe but for many players](https://github.com/recursecenter/wiki/wiki/System-Design)


## References
Bytebytego alex xu system design
15min intro to distributed systems - https://www.youtube.com/watch?v=k10_trKtKNk
Raft consensus algorithm with viz - https://raft.github.io/
Designing Data Intensive Applications - Martin Kleppmann
[Mastering Chaos - A Netflix Guide to Microservices](https://www.youtube.com/watch?v=CZ3wIuvmHeM)
[Introduction to Microservices, Docker, and Kubernetes](https://www.youtube.com/watch?v=1xo-0gCVhTU) - James Quigley 
[MIT 6.824](https://www.youtube.com/playlist?list=PLrw6a1wE39_tb2fErI4-WkMbsvGQk9_UB)
[DockerSwarm vs Kubernetes](https://circleci.com/blog/docker-swarm-vs-kubernetes/)
[Thorough Introduction to Distributed Systems](https://www.freecodecamp.org/news/a-thorough-introduction-to-distributed-systems-3b91562c9b3c/)
Paper on [Software Technologies for Developing Distributed Systems: Objects and Beyond ](https://www.dre.vanderbilt.edu/~schmidt/PDF/CSI-article.pdf)
Topics in distributed systems https://youtu.be/BkSdD5VtyRM
Books on System Design - https://github.com/Nitin96Bisht/System-Design/
build state machines from code - https://stately.ai/viz
brooker.co.za/blog - 
Ben and Greg Linux Performance
Every Computer Performance Book
Berkley Packet Filter* bpf performance tools
Observability Engineering - Liz Fong Jones
[Conductor](https://github.com/Netflix/conductor) - microservices orchestration by Netflix


Current
Learn system design

Links
Daily alex xu system design posts

Outlines
0105-
System design interview by alex xu
Scale from zero to millions of users
Single server setup - user sends api call to DNS, DNS calls web server, web server sends HTML, user receives HTML in browser
Database
Relational - perform join operations across tables
Non-relational - super low-latency, unstructured data, serialize and deserialize, need to store massive amounts
Vertical scaling vs horizontal scaling - stronger computer vs more computers
Load balancer - distribute incoming traffic among web servers
Database replication - better performance, reliability, high availability
Master db - only supports write, when down slave can do writes
Slave - only supports read, when down master can do reads
Cache
Back of the Envelope Estimation - thought experiments + common performance numbers to get good feel for which designs will meet your requirements
A Framework for System Design Interviews - 4 step process for effective interview
[3-10min] Understand problem and establish design scope
What specific features are we going to build?
How many users does the product have?
How fast does the company anticipate to scale up? What are the anticipated scales in 3mos, 6mos, 1y
What is company’s tech stack? What existing services you might leverage to simplify the design?
[10-15min] Propose high-level design and get buy-in - back of the envelope calculation
[10-25min] Design deep-dive
[3-5min] Wrap up
Design a Rate Limiter
Design Consistent Hashing
Design a Key-Value Store - applying framework to specific problem
Understanding problem
System diagram
Considerations - replication, outages
Summary
Design a Unique ID Generator in Distributed Systems
Design a URL Shortener
Design a Web Crawler
Design a Notification System
Design a News Feed System
Design a Chat System
Design a Search Autocomplete System
Design Youtube
Understand problem
High-level design - video upload flows
Deep-dive - geographies, optimizations
Wrap up
Design Google Drive
The Learning Continues
Real World Systems - list of examples
Company engineering blogs
Additional reading - DDIA

Updates
0119
Strategies for deploying to production - Alex Xu system design post
Feature toggle - no downtime, targeted users

2023
1219
Notes System design interview with ML Engineer

Other books
System design
Ddia
Design patterns by martin fowler
Machine Learning System Design Interview by Alex Xu
Twitter
Netflix
Doordash
Bumble
