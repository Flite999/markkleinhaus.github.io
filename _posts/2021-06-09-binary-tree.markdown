---
layout: post
title:  "Implementing a binary tree"
date:   2021-06-09
categories: algorithms
---

Python - 

```
class Node:
  def __init__(self, data):
    self.data = data
    self.right = None
    self.left = None
  
  def __str__(self):
    return str(self.data) # pretty print the Node object

class BinaryTree:
  def __init__(self):
    self.root = None

  def addNode(self, data):
    if (self.root == None):
      self.root = Node(data)

    else:
      current = self.root

      while True:
        if (data < current.data):
          if current.left:
            current = current.left
          else:
            current.left = Node(data)
            break
        elif (data > current.data):
          if current.right:
            current = current.right
          else:
            current.right = Node(data)
            break
        else:
          break

  def inOrderTraversal(self, node):
    if node is not None:
      self.inOrderTraversal(node.left)
      print(node.data)
      self.inOrderTraversal(node.right)

vals = [1,6,8,3,6,9,8]
tree = BinaryTree()
for val in vals:
  tree.addNode(val)

tree.inOrderTraversal(tree.root)

```
