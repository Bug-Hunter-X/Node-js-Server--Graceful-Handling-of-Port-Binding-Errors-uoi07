# Node.js Server: Graceful Port Binding Error Handling

This repository demonstrates a common issue in Node.js server development: the lack of explicit error handling when attempting to bind to an already occupied port.  A robust server should gracefully handle such situations to avoid silent failures.

## The Problem

When a Node.js server tries to bind to a port that's already in use, it typically fails silently. This can make debugging difficult, as there's no immediate indication of the problem. 

## The Solution

This improved example shows how to use the `'error'` event listener on the `http.Server` object to detect the `'EADDRINUSE'` error (port already in use). The solution then logs a clear error message and exits the process cleanly.

## How to Run

1. Clone the repository.
2. Navigate to the repository directory.
3. Run `node bug.js` (the buggy version).
4. Run `node bugSolution.js` (the improved version) to observe the graceful error handling.  Try running this after having `bug.js` still running.

## Improvements

* Explicit error handling for `EADDRINUSE`.
* Informative error messages to aid debugging.
* Clean process exit on error.