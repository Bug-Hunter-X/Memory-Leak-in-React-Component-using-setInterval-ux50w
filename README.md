# React setInterval Memory Leak
This repository demonstrates a common bug in React applications involving memory leaks caused by the improper use of the `setInterval` function within the `useEffect` hook.

## Bug Description
The `MyComponent` component uses `setInterval` to update a counter every second. However, it fails to return a cleanup function from the `useEffect` hook, resulting in a memory leak.  The interval continues to run even after the component unmounts.

## Solution
The solution involves returning a cleanup function from the `useEffect` hook that uses `clearInterval` to stop the interval when the component unmounts.