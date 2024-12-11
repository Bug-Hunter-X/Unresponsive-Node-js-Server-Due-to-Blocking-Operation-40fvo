# Unresponsive Node.js Server Due to Blocking Operation

This repository demonstrates a common issue in Node.js where a long-running synchronous operation in a request handler blocks the event loop, making the server unresponsive.  The `bug.js` file shows the problem, and `bugSolution.js` provides a solution using asynchronous operations.

## Problem

The server in `bug.js` simulates a long-running task that keeps the CPU busy for 5 seconds. During this time, the server cannot handle any other requests, leading to unresponsiveness.

## Solution

The solution in `bugSolution.js` uses asynchronous operations to avoid blocking the event loop.  This allows the server to continue handling requests even while the long-running task is executing.

## How to reproduce the issue

1. Clone the repository.
2. Run `node bug.js`.
3. Try to make multiple requests to the server (e.g., using `curl` or a browser). You'll notice that after the first request, subsequent requests will hang.

## How to solve the issue

1. Implement asynchronous operations within the request handlers to avoid blocking the event loop.
2. Use appropriate asynchronous programming techniques like Promises, async/await, or callbacks to handle time-consuming operations.