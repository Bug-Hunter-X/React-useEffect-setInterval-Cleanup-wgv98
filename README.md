# React useEffect Hook: Missing Cleanup in setInterval

This repository demonstrates a common bug in React applications involving the `useEffect` hook and the `setInterval` function.  Failing to properly clean up the interval leads to memory leaks and unpredictable behavior.

## The Bug

The `bug.js` file contains a component that uses `setInterval` to update a counter every second.  However, it's missing a crucial return statement within the `useEffect` cleanup function. This means the interval continues to run even after the component unmounts, creating a memory leak.

## The Solution

The `bugSolution.js` file shows the corrected implementation. The `useEffect` hook now includes a return function that uses `clearInterval` to stop the interval when the component is unmounted. This prevents memory leaks and ensures the expected behavior.

## How to reproduce the bug

1. Clone the repository
2. Open `bug.js` and run the component
3. Observe the counter incrementing in the console even after the component is unmounted or navigated away from. 

## How to fix it

1.Refer to the `bugSolution.js` for the correct implementation.
2.Ensure to always return a cleanup function from `useEffect` that clears any interval, timeout, or other cleanup tasks using the appropriate methods like `clearInterval` and `clearTimeout`.