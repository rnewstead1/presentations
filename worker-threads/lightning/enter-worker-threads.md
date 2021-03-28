![Diagram](https://images.zenhubusercontent.com/570533156caf56c9d38f6ac7/1f840514-1e62-4a51-a973-7330cda15d8f)
Note: like multiple threads but running in the same process.
each worker has its own instance of V8 and the event loop
exchange info with the main process using message processing
so we avoid the race condition problems that threads have
share memory between threads using `SharedArrayBuffer`
this doesn't mean that Node.js is now multi-threaded.
because they don't introduce multi-threading language features to JavaScript itself.
Instead worker threads provide concurrency by allowing applications to use multiple isolated JS workers.
Node provides the comms between workers and the parent worker.
