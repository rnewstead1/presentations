Enter worker threads


isolated contexts
Note: each worker has its own instance of V8 and the event loop


exchange info with the main process using message processing
Note: They exchange info with the main process using message passing, so we avoid the race condition problems that threads have


live in the same process
Note: But as they live in the same process they use a lot less memory than forking the process


share memory between threads using `SharedArrayBuffer`

Note: So you can do CPU-intensive tasks with large amounts of data


Does this mean Node.js is now multi-threaded?


![Diagram](https://images.zenhubusercontent.com/570533156caf56c9d38f6ac7/1f840514-1e62-4a51-a973-7330cda15d8f)

Note: No - because they don't introduce multi-threading language features to JavaScript itself.
Instead worker threads provide concurrency by allowing applications to use multiple isolated JS workers.
Node provides the comms between workers and the parent worker.
