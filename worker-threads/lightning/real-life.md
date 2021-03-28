![performance graph](https://images.zenhubusercontent.com/570533156caf56c9d38f6ac7/40d8141f-6194-4c0c-9bcb-2b5a5b7f0ceb)
Note: I tried to find examples of people using this in production.
Some mentioned usages are encryption, and machine learning.
This graph shows the performance comparison of 3 Node.js servers which accept a string and returns a Bcrypt hash with 12 salt rounds.
A Bcrypt hash is a password-hashing function.
A salt is random data used as an additional input to the function.
So 12 salt rounds means the calculation to get to the hash is done 2^12 times
The 3 servers are:
- server with no multi-threading
- server with multi-threading but without thread pooling
- server with a thread pool of 4 threads
You can see from the graph that using a thread pool is significantly faster as there are more requests per second.
