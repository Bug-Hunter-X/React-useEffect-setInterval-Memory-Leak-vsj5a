# React useEffect setInterval Memory Leak

This repository demonstrates a common error in React applications involving the `useEffect` hook and `setInterval`.  Failure to properly clean up the interval leads to a memory leak, preventing the component from properly unmounting and potentially causing performance issues.

## Bug Description

The `MyComponent` uses `useEffect` to set an interval which increments a counter every second.  However, it lacks a cleanup function to stop the interval when the component unmounts. This causes the counter to continue incrementing indefinitely, leading to a memory leak.

## Solution

The solution involves returning a cleanup function from the `useEffect` callback. This cleanup function will clear the interval when the component unmounts. 