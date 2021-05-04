---
title: "Dynamic Programming"
date: 2021-02-23
tags: [Python]
excerpt: " "
---

Dynamic programming is particularly useful for optimizing recursive problems that can be broken down into smaller subproblems. The brute force recursive solution often computes a subproblem multiple times and is not as efficient as the top down or bottom up approach to dynamic programming. The most common problem that uses this approach is the calculation of Fibonacci numbers, where the next number in the sequence is defined as the sum of the previous two.

### Top Down - Memoization
The top down approach involves starting with the larger problem and solving smaller subproblems until the base case is reached and an answer is returned. A recursive function can be written to obtain the nth number in the sequence by calling fib(n) and returning fib(n-1) + fib(n-2) which would in turn calculate earlier numbers in the sequence until reaching the base case fib(2) which is equal to fib(0) + fib(1) = 1. The code for this shown below. 

```python
def fibRecursive(n):
    if n < 2:
        return n
    return fibRecursive(memoize, n-1) + fibRecursive(n-2)   
```

Since the calculation of the nth fibonacci number is a term in the calculation of both fib(n+1) and fib(n+2), the function would be called with the same input twice. As n grows larger, the number of duplicate calls increase dramatically. If we could instead store this result the first time we calculate it, we could avoid calling same function multiple times. This is the idea behind memoization, and the code for this is shown below. 

```python
def fib(n):
    memoize = [-1 for x in range(n+1)]
    return fibRecursive(memoize, n)
def fibRecursive(memoize, n):
    if n < 2:
        return n
    if memoize[n] >= 0:
        return memoize[n]
    memoize[n] = fibRecursive(memoize, n-1) + fibRecursive(n-2)   
    return memoize[n]
```

### Bottom Up - Tabulation
The bottom up approach solves the subproblems first before buildign up to the final solution. It is called tabulation because the results of the subproblems are usually stored in a table format that is filled up dynamically as subproblems get evaluated. In the simple scenario of Fibonacci numbers, a one-dimensional array is enough to build up the answer bottom up. In more complicated dynamic programming problems, a two-dimensional array or matrix may be used. 

```python
def fib(n):
    dp = [0,1]
    for i in range(2, n+1):
        dp.append(dp[i-1] + dp[i-2])
    return dp[n]
```




