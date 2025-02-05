# React useEffect Hook Memory Leak and Race Condition
This repository demonstrates a common error in React applications involving the `useEffect` hook: forgetting to include a cleanup function to handle memory leaks and race conditions when fetching data. The `bug.js` file contains the buggy code, while `bugSolution.js` provides the corrected version.

## Bug Description
The buggy code uses `useEffect` to fetch data without a cleanup function.  If the component unmounts before the fetch completes, it can lead to memory leaks.  Repeated fetches before the previous ones resolve can cause race conditions leading to unpredictable behaviour and potential errors.

## Solution
The solution demonstrates the importance of adding a cleanup function to the `useEffect` hook. This function is responsible for canceling any ongoing asynchronous operations (like fetches) when the component unmounts, preventing memory leaks and handling race conditions effectively.

## How to Reproduce
1. Clone this repository.
2. Run `npm install`
3. Run `npm start` (or your preferred method to run React project) to view the buggy component.
4. Observe the console for potential errors or unexpected behavior.
5. Refer to `bugSolution.js` for the fixed code.

This example highlights the significance of careful cleanup in asynchronous operations within React components.