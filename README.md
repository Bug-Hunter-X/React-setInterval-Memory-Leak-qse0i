# React setInterval Memory Leak

This repository demonstrates a common mistake in React applications: using `setInterval` within a `useEffect` hook without proper cleanup. This can lead to memory leaks and unexpected behavior.

The `bug.js` file showcases the incorrect implementation. The `bugSolution.js` file provides the corrected code.

## Bug Description
The `setInterval` function, if not properly cleared, will continue to run even after the component unmounts. This leads to increased memory usage and potential performance issues.  The issue is that the interval continues indefinitely without being stopped.

## Solution
The solution involves returning a cleanup function from the `useEffect` hook. This function will clear the interval when the component unmounts or when the dependency array changes.