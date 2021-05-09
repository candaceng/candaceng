---
title: "Divide and Conquer Algorithm"
date: 2021-04-23
tags: [Data Structures and Algorithms]
excerpt: "Divide, conquer, combine"
---

The divide and conquer algorithm is an approach comprised of three steps: divide, conquer, and combine. It is a method that involves breaking down a large problem and recursing over smaller subproblems. This method is similar to [dynamic programming]({% link _posts/2021-02-23-dynamic-programming.md %}) except the results of the subproblems are not stored for future reference are not evaluated multiple times. Some common applications of this algorithm are outlined below. 

### Merge Sort and Quick Sort
There are many different ways to sort an array of numbers, and the merge sort algorithm is one of the fastest for large arrays. Its divide and conquer approach involves repeatedly halving the array until they become individual numbers. They are then rebuilt in the same way they were deconstructed, and are sorted before merging. 

Quick sort also uses a divide and conquer approach; however, the partitions made are not necessarily half of the array each time. Instead, a pivot is randomly chosen, and two pointers at each end of the array are used to swap numbers that should be to the left/right of the chosen pivot. We end up with two smaller subarrays, and another iteration of quick sort is evaluated for both, where a pivot is randomly chosen and numbers are swapped accordingly. This process is repeated until the array is sorted. 

These algorithms are recursive, and the recurrence relation can be broken down to derive the time complexity. It turns out that both algorithms run in O(nlogn) time in an ideal scenario. 

### Fast Fourier Transform
In digital signal processing, the Fast Fourier Transform is a divide and conquer algorithm designed to be an efficient approach to computing the discrete Fourier transform. Our goal is to multiply two polynomials in less than O(n<sup>2</sup>) time. This can be achieved if the coefficient representations of the two polynomials are converted to its corresponding value representations, and converted back after multiplication. the FFT algorithm does this by splitting the polynomial into odd and even terms. A recursive function is called on the each half and the final answer is rebuilt from these two parts to obtain the value representation of the final polynomial. It turns out that this algorithm also runs in O(nlogn) time as with the merge sort and quick sort algorithms above.



