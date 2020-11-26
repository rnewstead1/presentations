## An example


```js
//index.js
// run with node --experimental-work index.js on Node.js 10.x
const { Worker } = require('worker_threads');

function runService(workerData) {
	return new Promise((resolve, reject) => {
    	const worker = new Worker('./service.js', { workerData });
        worker.on('message', resolve);
        worker.on('error', reject);
        worker.on('exit', (code) => {
        	if (code !== 0) {
            	reject(new Error(`Worker stopped with exit code ${code}`));
            }
        });
        
    });
}

async function run() {
	const result = await runService('world');
    console.log(result);
}

run().catch(err => console.error(err));
```

Note: this creates a Worker thread, and give it some data.
The API is event-driven.
It is wrapped in a Promise that resolves in the first message received from the Worker.
So - we pass the filename as an argument and the data we want the Worker to process.
There are two main ways of starting a worker:
- `new Worker(filename)`
- `new Worker(code, { eval: true })`
\The latter will execute the code you pass it (probably don't do this in production...)
Remember - the data is cloned and not in any shared memory.
Then we wait for the Worker thread to send us a message by listening to the `message` event.


```js
const { workerData, parentPort } = require('worker_threads');

// You can do any CPU-heavy stuff here, in a synchronous way
// without blocking the "main thread"
parentPort.postMessage({ hello: workerData });
```

Note: the service looks like this.
So here we need:
- `workerData` sent from the main app
- a way to return information to the main app
This is done with the `parentPort.postMessage()`
we call this with the result of our processing


![diagram](https://images.zenhubusercontent.com/570533156caf56c9d38f6ac7/217e1167-9f6e-4041-beb2-c6d4fd470c54)
