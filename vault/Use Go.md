
Good for [[System Design]] because:
easy devops

Good for CLI tools because:
easy devops, elegant interfaces

Go has garbage collection
Good for cloud services
Latest descendant of Java family

Go provides:
* concurrent execution (goroutines)
* synchronization and messaging (channels)
* multi-way concurrent control (select)

Questions
* How do closures make concurrency easier to express?
* What's multiplexing?
* Why does docker use Go? easier devops with stable dependencies

## Intros
1. [Demo of goroutines and channels](https://www.youtube.com/watch?v=oV9rvDllKEg)
2. [Concurrency patterns](https://www.youtube.com/watch?v=f6kdp27TYZs)
3. [Advanced concurrency patterns](https://www.youtube.com/watch?v=QDDwwePbDtw)
4. [100 Go Mistakes](https://www.manning.com/books/100-go-mistakes-and-how-to-avoid-them)

Tools
[Tour of Go](https://go.dev/tour/welcome/1)

## Things you can use
[Samples](https://go.dev/talks/2012/waza.slide#45), easily write the following:
Load balancer
Dispatch
Query replicated database
Reduce golang inage from 45mb to 4mb with this hack: https://www.linkedin.com/posts/anton-putra_i-didnt-know-it-was-possible-to-reduce-a-activity-7232847713954938880-7PNS?utm_source=share&utm_medium=member_android

## Concepts
* Concurrency - composition of independently executing things, vs parallel - simultaneous execution of independent things
	* no need to wait for something to finish
	* no need to start at the same time
* Goroutines - lightweight thread managed by Go runtime
* Channels - typed conduit through which you can send and receive values
* Mutex - mutual exclusion, only one goroutine can access a variable at a time to avoid conflicts

Software made with go
Docker
Mqtt

References
distributed systems from the ground up! (Go) https://www.oreilly.com/library/view/cloud-native-go/9781492076322/
distributed services with go - https://pragprog.com/titles/tjgo/distributed-services-with-go/