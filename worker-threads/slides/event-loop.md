Node.js has the event loop

Note: Node is able to be asynchronous and have non-blocking I/O because of the event loop.
We can offload operations to the system kernel wherever possible via callbacks, promises and async/await.
Go check out [Charlotte's post on our blog](https://engineering.tes.com/post/asynchronous-javascript) about asychronous code!


The kernel can run I/O in parallel for us
Note: The kernel can run I/O in parallel for us
When it's time to send data back to our JS code, the JS part runs in a single thread.


![event loop](https://qph.fs.quoracdn.net/main-qimg-ff39ad46d7fbc5cde9cb412ca6f57bd9.webp)


This is great if all we do is asynchronous I/O

Note: Our code consists of small portions of synchronous blocks that run fast and pass data to files and streams.
Our code is so fast that it doesn't block the execution of other pieces of JS.
We spend more time waiting for I/O events to happen than for JS code to be executed.
