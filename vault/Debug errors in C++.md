[[Debug errors]]

Protip
If so many errors in compiler, probably a template

Tools:
Gdb
```
g++ -o hello -g hello.cpp
gdb
file hello // specify what file to check
b main // set breakpoint to "main" function
r // run program
s // step 1 line
p x // print out variable x
n // if next step is function, skip call
c // continue until end
where // list call stack up to where you are in the program
```
https://people.astro.umass.edu/~weinberg/a732/gdb.html#SEC99

lldb
```
breakpoint set -f file.zig -l 156
thread backtrace
```

Addr2line
Convert addresses into filenames and line numbers, use when there is a crash on specific address

Detects segfaults with Valgrind
Detects concurrency issues with Helgrind