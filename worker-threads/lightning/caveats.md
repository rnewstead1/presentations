## Caveats


spawning a Worker can be expensive
Note: Even though it's more lightweight than forking a process
spawning a Worker involves some serious work and can be expensive if you do it frequently.
use a pool if you are creating a lot of Workers TODO is there a lib for this??


not cost-effective for lots of I/O intensive work
Note: Worker threads are useful if you're doing a lot of CPU-intensive work.
But not cost-effective if you're doing lots of I/O intensive work.
Asynchronous I/O operations are more efficient than Workers can be


will not improve CPU usage
Note: Worker threads may improve performance,
But the CPU usage will be the same (or more) as the workers consume a lot of CPU
