# React Memory Leak: setInterval in useEffect without cleanup

This repository demonstrates a common React memory leak caused by improper use of `setInterval` within the `useEffect` hook.  The issue occurs because the interval is not properly cleared when the component unmounts. This leads to unnecessary function calls and a potential memory leak.

## Problem

The `bug.js` file contains a React component that uses `setInterval` to update a counter every second. However, it fails to clear the interval using `clearInterval` before the component is unmounted. This results in the interval continuing to run indefinitely, even after the component is removed from the DOM. 

## Solution

The `bugSolution.js` file demonstrates the correct way to use `setInterval` within `useEffect`. It includes a cleanup function to clear the interval when the component unmounts, preventing the memory leak.