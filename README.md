# React useEffect Infinite Loop Bug

This repository demonstrates a common React bug involving an infinite render loop caused by the `useEffect` hook.  The `bug.js` file contains the buggy code, while `bugSolution.js` provides the corrected version.

## Bug Description

The issue stems from omitting the dependency array in the `useEffect` hook.  When the dependency array is absent, or if it's incomplete, the effect will run after every render, leading to an infinite loop in this particular example, because the `console.log` triggers a re-render in this simplified case. This can cause your application to become unresponsive.

## How to Reproduce

1. Clone the repository.
2. Run `npm install` to install the dependencies.
3. Run `npm start` to start the development server.
4. Observe the infinite loop in your browser's console.

## Solution

The correct version is in `bugSolution.js`.  The key fix is adding the `count` variable to the dependency array of `useEffect` to specify that the effect only runs when the `count` state changes. This prevents the infinite loop.

## Learning Points

* Always include a dependency array in `useEffect` to avoid unexpected behavior and infinite render loops.
* Carefully consider what variables should be included in the dependency array for efficient React updates.