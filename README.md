# useEffect Cleanup Function Timing Issue in React
This repository demonstrates a common but subtle issue with the `useEffect` hook in React.  The cleanup function within `useEffect` is intended to execute before the component unmounts, allowing for resource cleanup (e.g., canceling subscriptions, clearing timers). However, if the return statement within the `useEffect`'s callback is not structured correctly, this cleanup can happen immediately after the first render instead of before unmounting. This example shows how to avoid the problem and how to structure your useEffect correctly. 

## How to Reproduce
1. Clone this repository.
2. Run `npm install`.
3. Run `npm start`.
4. Observe that 'Component unmounting' logs before 'Component mounted'.  This is unexpected behavior.

## Solution
The solution involves correct structuring of useEffect. The cleanup function should only be executed when the component is unmounting. 

## Additional Notes
This issue highlights the importance of understanding the lifecycle methods and how the cleanup functions in useEffect are called. Pay close attention to the timing and ordering of these callbacks when developing your React application.