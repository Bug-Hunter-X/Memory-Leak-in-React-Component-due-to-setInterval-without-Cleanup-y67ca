# React setInterval Cleanup Issue

This repository demonstrates a common issue in React applications involving the improper use of `setInterval` within the `useEffect` hook.  Failing to clean up the interval leads to memory leaks and unexpected behavior.

## The Problem
The `bug.js` file shows a React component that uses `setInterval` to update a counter every second.  However, it lacks the necessary cleanup function to stop the interval when the component unmounts. This causes the interval to continue running indefinitely, even after the component is removed from the DOM, resulting in a memory leak.

## The Solution
The `bugSolution.js` file presents the corrected code.  The key change is the addition of a return function within the `useEffect` hook. This function clears the interval using `clearInterval` when the component unmounts, preventing the memory leak.  This ensures that resources are properly released.