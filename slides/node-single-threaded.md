So... Node.js is single-threaded?

Note: kind of...
We can run things in parallel.
But we don't create threads. 
And we don't sync them.


A Node.js process has:
- one process
- one thread
- one event loop
- one Javascript engine instance
- one Node.js instance
