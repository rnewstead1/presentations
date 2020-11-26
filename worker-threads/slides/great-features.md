## Features of Worker threads


A `SharedArrayBuffer` is accessible from multiple threads
Note: So you can share memory between threads - but limited to binary data
These array buffers are used with the `Atomics` module.
It lets you do some processes concurrently via a set of static functions.
It makes sure predictable values are written and read
that operations are finished before the next operation starts
that operations are not interrupted.


`MessagePort` is used for communicating between threads
Note: (as shown in the example).
This can be used to transfer structured data, memory regions and other MessagePorts between different Workers.


`MessageChannel` is an async two-way communication channel
Note: for communicating between different threads.
Each end of this channel is called a port.


`WorkerData` is used to pass startup data.
Note: An arbitrary JS value that contains a clone of the data passed to this thread's Worker constructor.
The data is cloned as if using `postMessage()`


`isMainThread`
Note: a boolean that is true if the code is not running inside a Worker thread
(e.g. you may only want to spawn a new Worker thread from the main thread) 
This can be useful if you're working with multiple threads in the same file.
