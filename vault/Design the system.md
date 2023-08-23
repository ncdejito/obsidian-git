
Design process from research
https://maheshba.bitbucket.io/blog/2023/07/12/Design.html

Scalable systems  
[https://www.linkedin.com/posts/garrytan_how-we-reduced-the-cost-of-building-twitter-activity-7097287204028239872-nBqn?utm_source=share&utm_medium=member_android](https://www.linkedin.com/posts/garrytan_how-we-reduced-the-cost-of-building-twitter-activity-7097287204028239872-nBqn?utm_source=share&utm_medium=member_android)

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


