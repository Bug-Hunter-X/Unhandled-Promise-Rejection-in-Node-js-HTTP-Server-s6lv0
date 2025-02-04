# Unhandled Promise Rejection in Node.js HTTP Server

This repository demonstrates a common error in Node.js servers where unhandled promise rejections within asynchronous operations can lead to silent failures. The server continues to run, but the client doesn't receive a proper response, and the error is only logged to the console.

## Problem

The `bug.js` file showcases a Node.js HTTP server that performs an asynchronous operation (`doSomethingAsync`).  This operation might throw an error, but the error is only caught locally within the `then().catch()` block.  No mechanism exists to properly send an error response to the client.

## Solution

The `bugSolution.js` file demonstrates a corrected implementation that handles errors effectively by sending an appropriate error response to the client (e.g., a 500 Internal Server Error) when exceptions occur during asynchronous operations.  It gracefully handles exceptions, ensuring a better user experience and providing more informative debugging information.