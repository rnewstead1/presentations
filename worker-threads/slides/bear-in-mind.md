## Some things to bear in mind


spawning a Worker can be expensive
Note: Even though it's more lightweight than forking a process (or using `cluster`),
spawning a Worker involves some serious work and can be expensive if you do it frequently.


use a pool if you are creating a lot of Workers


not cost-effective for lots of I/O intensive work
Note: Worker threads are useful if you're doing a lot of CPU-intensive work.
But not cost-effective if you're doing lots of I/O intensive work.
Asynchronous I/O operations are more efficient than Workers can be
The docs for Worker threads also tell you this.


will not improve CPU usage
Note: Worker threads may improve performance,
But the CPU usage will be the same (or more) as the workers consume a lot of CPU
