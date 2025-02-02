# TypeScript Closure Issue with setTimeout

This repository demonstrates a common error encountered when using `setTimeout` within a loop in TypeScript (and JavaScript).  The problem arises due to how closures capture variables.

## The Problem
The `printNumbers2` function attempts to print numbers from 1 to n with a slight delay using `setTimeout`.  However, due to the closure, all callbacks refer to the final value of `i`, which is `n + 1`. This leads to printing `n + 1` n times instead of the expected sequence of numbers from 1 to n.

## Solution
The solution involves using an immediately-invoked function expression (IIFE) to create a new scope for each iteration of the loop, effectively capturing the correct value of `i` for each callback.