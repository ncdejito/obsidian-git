
Good for [[Distributed Systems]] because:
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

## Concepts
* Concurrency - composition of independently executing things, vs parallel - simultaneous execution of independent things
	* no need to wait for something to finish
	* no need to start at the same time
* Goroutines - lightweight thread managed by Go runtime
* Channels - typed conduit through which you can send and receive values
* Mutex - mutual exclusion, only one goroutine can access a variable at a time to avoid conflicts