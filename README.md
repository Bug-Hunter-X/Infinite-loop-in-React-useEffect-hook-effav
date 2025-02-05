# React useEffect Infinite Loop Bug

This repository demonstrates a common React bug: an infinite loop caused by an incorrectly configured `useEffect` hook. The bug occurs when the `useEffect` hook's dependency array includes the state variable that's updated within the effect itself.  This creates a loop where the effect continuously updates the state, triggering another render and another execution of the effect.

## How to reproduce

1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `npm start` to start the development server.
4. Observe the error message in the console and the rapid updates of the counter in the browser.

## Solution

The solution involves correctly managing the dependencies of the `useEffect` hook. In this specific case, removing `count` from the dependency array prevents the infinite loop. The `useEffect` will only run once after the initial render. If you need to run the effect only when `count` changes, you could add an additional dependency that triggers the effect only under certain conditions.