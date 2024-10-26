Protocols - defines the rules, syntax, semantics and synchronization of communication and possible error recovery methods.
ex. HTTP, TCP, IP, UDP

* UDP - 
	no handshaking dialogues, and thus exposes the user's program to any [unreliability](https://en.wikipedia.org/wiki/Reliability_(computer_networking) "Reliability (computer networking)") of the underlying network; there is no guarantee of delivery, ordering, or duplicate protection.
	Time-sensitive applications often use UDP because dropping packets is preferable to waiting for packets delayed

* TCP
	 connection between client and server is established before data can be sent
	 Three-way handshake (active open), retransmission, and error detection adds to reliability but lengthens latency

Handshaking - automated process of negotiation between two participants (example "Alice and Bob") through the exchange of information that establishes the protocols of a communication link at the start of the communication, before full communication begins.
