# Node.js Server Unresponsiveness

This repository demonstrates a common issue in Node.js where a long-running operation in the request handler blocks the event loop, causing the server to become unresponsive. The `server.js` file contains the buggy code, while `serverSolution.js` provides a solution using asynchronous operations.

## Problem
The problem lies in the `while` loop within the request handler. This loop keeps the CPU busy for 5 seconds, preventing the event loop from processing other incoming requests during that time.  This leads to the server appearing unresponsive to new connections.

## Solution
The solution involves using asynchronous operations, such as `setTimeout` or promises, to avoid blocking the event loop.  The `serverSolution.js` file demonstrates the improved, non-blocking approach.