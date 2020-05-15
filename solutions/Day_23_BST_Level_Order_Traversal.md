# Day 23 : BST Level-Order Traversal
## Problem
#### Objective

Today, we're going to further with Binary Search Trees.

<br>

#### Task

A level-order traversal, also known as breadth-first search, visits each level of a tree's nodes from left to right, top to bottom. You are given a pointer, `root`, pointing to the root of a binary search tree. Complete the `levelOrder` function provided in your editor so that it prints the level-order traversal of the binary search tree.

**Hint** You'll find a queue helpful in completing this challenge.

<br>

#### Input Format

The locked stub code in your editor reads the following inputs and assembles them into a BST:
- The first line contains an integer, `T` (the number of test cases)
- The `T` subsequent lines each contain an integer, `data`, denoting the value of an element that must be added to the BST.

<br>

#### Output Format

Print the `data` value of each node in the tree's level-order traversal as a single line of `N` space-separated integers.

<br>

#### Sample Input


```
6
3
5
4
7
2
1
```

<br>

#### Sample Output


```
3 2 5 1 4 7
```

<br>

#### Explanation


The input forms the following binary search tree:

![](https://s3.amazonaws.com/hr-challenge-images/17176/1461696188-8eddd12300-BST.png)

We traverse each level of the tree from the root download, and we process the nodes at each level from left to right. The resulting level-order traversal is 3 -> 2 -> 5 -> 1 -> 4 -> 7, and we print these data values as a single line of space-separated integers.


<br>

## Given code

```python
import sys

class Node:
    def __init__(self,data):
        self.right=self.left=None
        self.data = data
class Solution:
    def insert(self,root,data):
        if root==None:
            return Node(data)
        else:
            if data<=root.data:
                cur=self.insert(root.left,data)
                root.left=cur
            else:
                cur=self.insert(root.right,data)
                root.right=cur
        return root

    def levelOrder(self,root):
        # write your code here

T=int(input())
myTree=Solution()
root=None
for i in range(T):
    data=int(input())
    root=myTree.insert(root,data)
myTree.levelOrder(root)
```


<br>

## Solution


```python
import sys

class Node:
    def __init__(self,data):
        self.right=self.left=None
        self.data = data
class Solution:
    def insert(self,root,data):
        if root==None:
            return Node(data)
        else:
            if data<=root.data:
                cur=self.insert(root.left,data)
                root.left=cur
            else:
                cur=self.insert(root.right,data)
                root.right=cur
        return root

    def levelOrder(self,root):
        tree = []
        queue = [root]
        while queue:
            node = queue.pop()
            tree.append(node.data)
            if node.left:
                queue.insert(0, node.left)
            if node.right:
                queue.insert(0, node.right)
        print(" ".join([str(i) for i in tree]))

T=int(input())
myTree=Solution()
root=None
for i in range(T):
    data=int(input())
    root=myTree.insert(root,data)
myTree.levelOrder(root)
```
