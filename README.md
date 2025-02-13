# Node.js Server Unresponsiveness

This repository demonstrates a common issue in Node.js where a long-running synchronous operation in the request handler can cause the server to hang or become unresponsive.  The example uses a `while` loop to simulate a blocking task. This is bad practice in Node.js, as it prevents the event loop from processing other requests.

## Bug
The `server.js` file contains the buggy code. Running this will cause the server to be unresponsive after handling a single request.  New requests will hang. 

## Solution
The `serverSolution.js` file demonstrates a fix using asynchronous operations or offloading long-running tasks to worker threads to avoid blocking the event loop.