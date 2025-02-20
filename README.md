# JavaScript Closure Issue with setTimeout

This example demonstrates a common issue in JavaScript involving closures and the `setTimeout` function.  The expected behavior is that the loop iterates and logs the values 0 through 9 with a one-second delay. However, due to how closures work in JavaScript, the output is unexpectedly all 10s.

## Problem

The problem stems from how the `setTimeout` callback function captures the variable `i`.  By the time the `setTimeout` callbacks finally execute, the loop has already completed, and `i` is its final value of 10.

## Solution

The solution involves using an immediately invoked function expression (IIFE) or `let` to create a new scope for each iteration of the loop, ensuring that each callback captures its own unique value of `i`.

This repository contains two files: `bug.js` (demonstrating the problem) and `bugSolution.js` (showing the corrected code).