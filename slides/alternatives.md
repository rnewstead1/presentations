What have we traditionally done instead?


Before worker threads we could:
- fork a process with `child_process.fork()`

Note: with this method the main process can communicate with the child process by sending and receiving events
No data is shared, data is "cloned".
You don't share memory so there are no race conditions.


Problems with this:
- expensive in terms of resources
- slow
- it means running a new VM from scratch using a lot of memory (since processes don't share memory) 

Note: Forking a process uses a lot of resources - so expensive, and slow.
And uses a lot of memory. 
So if you have multiple forked processes and reuse them it would use a lot of memory.
much more memory than a multi-threaded solution would use,
as threads are much lighter weight than forked processes.


Before worker threads we could:
- fork a process with `child_process.fork()`
- use the `cluster` module

Note: this lets you create multiple child processes which run on their own thread.
But this is also expensive.
Again it's multiple processes as it uses the `child_process.fork()` under the hood


Before worker threads we could:
- fork a process with `child_process.fork()`
- use the `cluster` module
- use a third-party module (like Microsoft's Napa.js)

Note: Napa.js is a multi-threaded JS runtime built on V8.
Exposed as a Node.js module.
It lets you execute JS in multiple V8 isolates and communicate between them.
But it's clunky to have rely on a module for this.


Web Workers API

Note: the browser already has the concept of multiple threads with the Web Workers API.
This is a more mature API for the web.
It is well supported by modern browsers.
Can be useful for:
- crypto
- compressing / decompressing
- image manipulation
- computer vision (e.g. face recognition)
in your web app.
