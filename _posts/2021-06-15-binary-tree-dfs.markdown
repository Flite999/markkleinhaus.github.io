---
layout: post
title:  "More depth first search for a binary tree"
date:   2021-06-15
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
        elif (data >= current.data):
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
  
  def preOrderTraversal(self, node):
    if node is not None:
      print(node.data)
      self.preOrderTraversal(node.left)
      self.preOrderTraversal(node.right)
  
  def postOrderTraversal(self, node):
    if node is not None:
      self.postOrderTraversal(node.left)
      self.postOrderTraversal(node.right)
      print(node.data)
     

vals = [1,6,8,3,6,9,8]
tree = BinaryTree()
for val in vals:
  tree.addNode(val)

print("Depth First Search")
print("-----")
print("in order traversal:")
tree.inOrderTraversal(tree.root)
print("pre order traversal:")
tree.preOrderTraversal(tree.root)
print("post order traversal:")
tree.postOrderTraversal(tree.root)



```
