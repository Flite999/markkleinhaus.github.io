---
layout: post
title:  "Determine Min Level on a bin tree - tough edge case"
date:   2021-08-13
categories: algorithms
---

Attempted [LeetCode #111](https://leetcode.com/problems/minimum-depth-of-binary-tree/) this morning and seemed like a simple enough exercise at first, then got hit with a surprising edge case, then really stumbled on it!

First solution is simply:

```

def minDepth(root):
  def dfs(node):
    if node is None:
      return 0

    return min(dfs(node.left), dfs(node.right)) + 1
  
  return dfs(root)

```

but this fails on the edge case where the input is a linked list like so:
[2,null,3,null,4,null,5,null,6]

```
2
  \
    3
      \
        4
          \
            5
              \
                6
```

no left child from the root.

had to look up the logic to capture that edge case after being stumped and found this nice solution.

```
def minDepth(root):
  def dfs(node):
    if node is None:
      return 0
    # None in list short circuits by returning when a match is found in the list, like any()
    # good for edge cases like a linked list, returns max of the current path
    if None in [node.left, node.right]:
      return max(dfs(node.left), dfs(node.right)) + 1
    else:
      return min(dfs(node.left), dfs(node.right)) + 1
        
  return dfs(root)

```

Learned about behavior when None is referencing a list of values, as well.


