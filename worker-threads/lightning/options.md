Pre worker threads:
- fork a process with `child_process.fork()`
- use the `cluster` module
- use a third-party module
Note: The first two are slow and expensive.
Forking a process uses a lot of CPU. Cluster uses that under the hood.
There are 3rd party modules like Microsoft's Napa.js, but this is additional complexity.
For JS running in the browser there is also the Web Workers API which is well supported by modern browsers.
Can be useful for:
- crypto
- compressing / decompressing
- image manipulation
- computer vision (e.g. face recognition)


```js
const worker = require('worker_threads');
```

available from Node `10.5.0`

stable from `12`
Note: pre `11.7.0` enable with `--experimental-worker` flag
