---
layout: post
title:  "Different Algorithm Solutions to the Common Elements problem"
date:   2021-06-07
categories: algorithms
---

Take two arrays:

A = [5,2,8,9,4]
B = [3,2,9,5]

How many elements exist in both lists? In this case, the answer is 3; 2,5,9 exist in both lists.

First approach - brute force, O($$n^2$$) method. Iterate through A, and check if the element exists in B.

```
class Main {
  public static void main(String[] args) {
    int[] arrA = new int[]{ 5,2,8,9,4 };
    int[] arrB = new int[]{ 3,2,9,5 };
    int result = 0;
    result = bruteMethod(arrA, arrB);
    System.out.println(result);
  }

  private static int bruteMethod(int[] first, int[] second) {
    int commonNum = 0;
    for (int i = 0; i < first.length; i++) {
      for (int j = 0; j < second.length; j++) {
        if (first[i] == second[j]) {
          commonNum ++;
        }
      }
    }
    return commonNum;
  }
}
```

2nd approach - binary search tree

3rd approach - heap structure