# Uncontrolled setInterval in useEffect
This example demonstrates a common issue in React components: the improper use of `setInterval` within the `useEffect` hook without a cleanup function.  This can lead to memory leaks and unexpected behavior.

## Problem
The `setInterval` function is used to update a counter every second. However, because there's no cleanup function within the `useEffect` hook, the interval continues indefinitely even after the component unmounts. This results in a memory leak as the interval continues to run in the background.

## Solution
The solution is to include a cleanup function within the `useEffect` hook to clear the interval when the component unmounts.  This ensures that the interval is properly stopped and prevents memory leaks.

## How to Reproduce
1. Clone this repository
2. Run `npm install`
3. Run `npm start`
4. Observe the counter incrementing every second.  Try navigating to another page, or refreshing the page, and look at console in developer tools to see that counter is still working. 
5. Then try with the solution.