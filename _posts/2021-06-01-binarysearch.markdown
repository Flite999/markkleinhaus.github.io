---
layout: post
title:  "Binary Search Study"
date:   2021-06-01
categories: algorithms
---

Halves a SORTED list by starting the search in the middle, checking if the current location is less than x or equal to/greater than x, and then makes the next jump to the right or left of the list correspondingly.

Method 1 in Python:
```
def methodOne(arr, x):
  a = 0
  b = len(arr)-1

  while (a <= b):
    k = int((a + b) / 2)
    if (arr[k] == x):
      return k
    
    if (arr[k] > x ):
      b = k - 1
    else:
      a = k + 1

testArr = [1,2,3,4,5,6,7,8]
arrLocation = methodOne(testArr, 5)
print(arrLocation)
```

Method 2 in Java:
```
class Main {
  public static void main(String[] args) {
    int[] testArr = new int[]{ 1,2,3,4,5,6,7 };
    int testInt = 5;

    String arrLocation = methodTwo(testArr, testInt);
    System.out.println(arrLocation);
  }

  public static String methodTwo(int[] arr, int x) {
    Integer k = 0;
    int n = arr.length;
    for (int b = n/2; b >= 1; b /= 2) {
      while (k + b < n && arr[k + b] <= x) {
        k += b;
      }
      
      if (arr[k] == x) {
        return k.toString();
      }
    }
    String err = "not found";
    return err;
  }
}
```

