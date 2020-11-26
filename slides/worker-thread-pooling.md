## Worker Thread Pooling


Use thread pooling if you frequently need to spin up Worker threads
Note: A Worker Thread Pool is a group of Node.js running worker threads which are available to be used for incoming tasks


When a new task comes in to the pool it can be passed to an available worker via the parent-child message channel


Once the worker completes the task it can pass the results back to the parent via the same channel

Note: The thread pool reduces the overhead of creating new threads.
However creating a large number of threads is not efficient as the number of parallel threads that can be run effectively is always limited by the hardware.
