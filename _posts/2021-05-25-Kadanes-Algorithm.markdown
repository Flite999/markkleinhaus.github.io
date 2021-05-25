---
layout: post
title:  "Kadane's Algorithm"
date:   2021-05-25
categories: algorithms
---

Determines the largest maximum contiguous subset of a set in O(n) time (brute force method is O(n^2) time).

```
def maxSumSubArray(arr):
  local_max = 0
  global_max = 0

  for int in arr:
    local_max = max(int, int + local_max)
    if (local_max > global_max):
      global_max = local_max
  return global_max

testArr = [-1,2,7,6,4,8,-9,2]
maxSum = maxSumSubArray(testArr)
print(maxSum)
```
Algorithm loops through the array once and compares the max between the current value in the array and the current value + previous local max value. Assigns that value to the local_max, and if it is larger than the current global_max value, replaces that.
