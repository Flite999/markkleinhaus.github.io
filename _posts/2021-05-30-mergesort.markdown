---
layout: post
title:  "Merge Sort Recursion and Call Stack Analysis"
date:   2021-05-30
categories: algorithms
---

Code taken from [towardsdatascience.com](https://towardsdatascience.com/introduction-to-recursion-and-merge-sort-2e143b1b7615)

```
def mergesort(arr):
    n = len(arr)
    if n == 1:
        return arr # sorting a single number :) easy!
    else:
        left_sorted = mergesort(arr[:n//2])
        right_sorted = mergesort(arr[n//2:])
        
    return merge(left_sorted, right_sorted) # have to define merge!

def merge(left, right):
    res = [] # store fully sorted array here
    while left and right: # both arrays are not empty
        if left[0] <= right[0]:
            res.append(left.pop(0))  # take first element
        else:                        # and put it to the result
            res.append(right.pop(0))
    res = res + left + right # left or right is empty at this point
                             # just append the rest, as it is sorted
    return res

testArr = [-2,8,6,3,5]
print(mergesort(testArr))
```

![recursion diagram](/assets/merge sort recursion.jpg)

1. First recursion call to left_sorted.
2. Another recursion call to left_sorted.
3. Base case is n == 1, so mergesort([-2]) returns.
4. Recursion call to right_sorted.
5. Base case is n == 1, so mergesort([-8]) returns.
6. We are back to [-2,8], recursive calls have popped off the stack, so now return merge([-2], [-8]).
7. Returns to original array.
8. Now a recursion call to right_sorted for the original array.
9. Recursion call to left_sorted.
10. Base case, return.
11. Recursion call to right_sorted.
12. Recursion call to left_sorted.
13. Base case, return.
14. Recursion call to right_sorted.
15. Base case, return.
16. Return merge(left_sorted, right_sorted).
17. Returns back to arr[6,3,5]
18. Return merge([6],[3,5])
19. Returns back to original array.
20. Return merge([-2,8],[3,5,6]), which finally returns the sorted array [-2,3,5,6,8].