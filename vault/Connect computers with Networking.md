[[Automate development (DevOps)]]
[[Protocols]]
[[Protocol buffers]]

## Special addresses
* 127.0.0.1 - your computer (localhost) 'fake' local only network - it can only be accessed internally (ie. not from outside the machine)
* 255.255.255.255 - broadcast address (group email address)
* 0.0.0.0 - use for dockerizing stuff, default or placeholder, 0.0.0.0 is all ports on the machine

## Definitions

Packets - small segment of a larger message. Data sent over computer networks*, such as the Internet, is divided into packets. 

DNS - domain name system, is the phonebook of the Internet, used to identify computers reachable through the Internet

Network Sockets - endpoint for sending and receiving data across the network
[[WebSockets]] - is a computer communications protocol, providing full-duplex (2-way) communication channels over a single TCP connection

Broadcast address - network address used to transmit to all devices connected to a multiple-access communications network. A message sent to a broadcast address may be received by all network-attached hosts. (like a group list email)

Datagram - basic unit associated with a packet-switched network (packet switching is a method of grouping data into packets that are transmitted over a digital network)

Endpoint - an interface exposed by a communicating party or by a communication channel. An example of the latter type of a communication endpoint is a publish-subscribe topic or a group in group communication systems.

Webhooks [tutorial](https://www.youtube.com/watch?v=41NOoEz3Tzc)

## Commands for troubleshooting
* `ufw` - Open a port on Linux with ufw - https://www.digitalocean.com/community/tutorials/opening-a-port-on-linux

* `telnet` - used to establish the connections between different machines.This command allows us to manage the remote devices using the CLI (command-line interface).  It uses TCP port 23 which is assigned to the telnet protocol, [source](https://linuxhint.com/linux-telnet-command/)

* `dig` - used to gather DNS information (Domain Information Groper) [source with examples](https://www.geeksforgeeks.org/dig-command-in-linux-with-examples/)
* `nslookup` - enter a host name (for example, "whatis.com") and find out the corresponding IP address or domain name system (DNS) record

* `netstat` - Displays active TCP connections, ports on which the computer is listening, Ethernet statistics, the IP routing table, IPv4 statistics (for the IP, ICMP, TCP, and UDP protocols), and IPv6 statistics (for the IPv6, ICMPv6, TCP over IPv6, and UDP over IPv6 protocols). Used without parameters, this command displays active TCP connections [source](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/netstat)

* `ping` - sends packets of data to a specific IP address on a network, and then lets you know how long it took to transmit that data and get a response. 

* `nc` (netcat) - tility for reading from and writing to network connections using TCP or UDP.

* `ifconfig` - "interface configuration." It is used to view and change the configuration of the network interfaces on your system.

Connect any usb device remotely as if you were connected locally
https://www.virtualhere.com/


## References
Networking concepts in flashcards
https://questions.wizardzines.com
