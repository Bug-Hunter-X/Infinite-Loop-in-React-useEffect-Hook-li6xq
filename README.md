# React useEffect Infinite Loop Bug

This repository demonstrates a common error in React applications involving the `useEffect` hook.  The `useEffect` hook is used to perform side effects after a component renders. However, if not used correctly, it can lead to infinite loops, crashing the application.

The `bug.js` file contains the buggy code. The `bugSolution.js` file provides a corrected version.

## Problem
The problem lies in the incorrect usage of the `useEffect` hook.  Updating the `count` state within the `useEffect` function creates an infinite loop because every update triggers a re-render, which in turn triggers the `useEffect` function again, leading to an endless cycle.

## Solution
The solution involves adding a dependency array to the `useEffect` hook. The dependency array specifies that the effect should only run when the values in the array change. By adding the `count` variable to the dependency array, the loop is broken because the effect only runs when the `count` variable changes which is controlled by user clicks outside of the effect.