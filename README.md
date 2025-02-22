# React 19: Stale Closures in useState

This repository demonstrates a common, yet easily missed, error in React 19 related to stale closures when updating state using `useState`.  The incorrect usage can lead to unexpected behavior and race conditions.

## Problem

When updating state with `useState`, directly using the state variable (`count`) within the updater function is incorrect. This is because React might batch updates or use the value of `count` from a previous render, causing unexpected results.  The correct approach is to use the functional update pattern with `prevCount => prevCount + 1`.  This ensures that the latest state value is always used.

## Solution

The solution file shows the correct approach using a functional update.  This guarantees that the update uses the most recent state value, avoiding stale closures and resulting in predictable state changes.

## Files

- `bug.js`: Demonstrates the incorrect usage of `useState`.
- `bugSolution.js`: Shows the correct usage of `useState` with functional updates.
