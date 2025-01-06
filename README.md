# Node.js Server Hang - Long-Running Synchronous Operation

This repository demonstrates a common Node.js issue: a server hanging due to a long-running synchronous operation blocking the event loop.

## Bug Description:
The `bug.js` file contains a simple HTTP server.  The request handler includes a loop that simulates a computationally expensive task. This synchronous operation blocks the event loop, preventing the server from responding to further requests.  The server appears unresponsive, and CPU usage will be very high.

## Solution:
The `bugSolution.js` file demonstrates how to solve this problem.  Instead of performing the long-running task synchronously, it uses asynchronous operations or offloads the work to worker threads to prevent blocking the main thread and allowing the server to remain responsive.