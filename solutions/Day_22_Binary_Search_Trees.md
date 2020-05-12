# Day 22: Binary Search Trees
## Problem
#### Objective

Today, we're working with Binary Search Trees (BSTs).

<br>

#### Task

The height of a binary search tree is the number of edges between the tree's root and furthest leaf. You are given a pointer, `root`, pointing to the root of a binary search tree. Complete the `getHeight` function provided in your editor so that it returns the height of the binary search tree.

<br>

#### Input Format

The locked stub code in your editor reads the following inputs and assembles them into a binary search tree:

- The first line contains an integer, `n`, denoting the number of nodes in the three.
- Each of the `n` subsequent lines contains an integer, `data`, denoting the value of an element that must be added to the BST.

<br>

#### Output Format

The locked stub code in your editor will print the integer returned by your `getHeight` function denoting the height of the BST.

<br>

#### Sample Input


```
7
3
5
2
1
4
6
7
```

<br>

#### Sample Output


```
3
```

<br>

#### Explanation


The input forms the following BST:

![](https://s3.amazonaws.com/hr-challenge-images/17175/1459894869-6bb53ce6eb-BST.png)


The longest root-to-leaf path is shown below:

![](https://s3.amazonaws.com/hr-challenge-images/17175/1459895368-4955f9ce74-LongestRTL.png)


There are 4 nodes in this path that are connected by 3 edges, meaning our BST's `height = 3`. Thus, we print `3` as our answer.

<br>

## Given code

```python
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

    def getHeight(self,root):
        #Write your code here

T=int(input())
myTree=Solution()
root=None
for i in range(T):
    data=int(input())
    root=myTree.insert(root,data)
height=myTree.getHeight(root)
print(height)  
```


<br>

## Solution


```python
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

    def getHeight(self,root):
        if root is None:
            return -1
        left_height = self.getHeight(root.left)
        right_height = self.getHeight(root.right)

        return 1 + max(left_height, right_height)


T=int(input())
myTree=Solution()
root=None
for i in range(T):
    data=int(input())
    root=myTree.insert(root,data)
height=myTree.getHeight(root)
print(height)       
```
