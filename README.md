# Stale Closure in React's useEffect Hook

This example demonstrates a common error in React's `useEffect` hook: a stale closure caused by an incorrect dependency array.

## Problem

The `setInterval` function within the `useEffect` hook uses the `count` variable from the initial render.  Because `count` is not included in the dependency array, it doesn't update when `setCount` is called.  This results in the counter not incrementing correctly.

## Solution

The solution is to include `count` in the dependency array, ensuring that the effect re-runs whenever the `count` value changes.

## How to reproduce:
1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `npm start` to start the development server.
4. Observe that the counter does not increment, indicating the stale closure problem.
5. Examine `bugSolution.js` to see the fix.