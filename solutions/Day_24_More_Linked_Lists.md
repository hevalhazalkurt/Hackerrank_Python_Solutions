# Day 24 : More Linked Lists
## Problem

#### Task

A Node class is provided for you in the editor. A Node object has an integer data field, `data`, and a `Node` instance pointer, `next`, pointing to another node (i.e.: the next node in a list).

A `removeDuplicates` function is declared in your editor, which takes a pointer to the `head` node of a linked list as a parameter.

Complete `removeDuplicates` so that it deletes any duplicate nodes from the list and returns the head of the updated list.

**Note** : The `head` pointer may be `null`, indicating that the list is empty. Be sure to reset your `next` pointer when performing deletions to avoid breaking the list.

<br>

#### Input Format

You do not need to read any input from stdin. The following input is hadled by the locked stub code and passed to the `removeDuplicates` function :
- The first line contains an integer, `N`, the number of nobes to be inserted.
- The `N` subsequent lines each contains an integer describing the `data` value of a node being inserted at the list's tail.


<br>

#### Constraints

The data elements of the linked list argument will always be in non-decreasing order.

<br>

#### Output Format

Your `removeDuplicates` function should return the head of the updated linked list. The locked stub code in your editor will print the returned list to stdout.

<br>

#### Sample Input


```
6
1
2
2
3
3
4
```

<br>

#### Sample Output


```
1 2 3 4
```

<br>

#### Explanation

`N = 6`, and our non-decreasing list is `{1,2,2,3,3,4}`. The values `2` and `3` both occur twice in the list, so we remove the two duplicate nodes. We then return ur updated (ascending) list, which is `{1,2,3,4}`.


<br>

## Given code

```python
class Node:
    def __init__(self,data):
        self.data = data
        self.next = None
class Solution:
    def insert(self,head,data):
            p = Node(data)           
            if head==None:
                head=p
            elif head.next==None:
                head.next=p
            else:
                start=head
                while(start.next!=None):
                    start=start.next
                start.next=p
            return head  
    def display(self,head):
        current = head
        while current:
            print(current.data,end=' ')
            current = current.next


    def removeDuplicates(self,head):
        # write your code here


mylist= Solution()
T=int(input())
head=None
for i in range(T):
    data=int(input())
    head=mylist.insert(head,data)    
head=mylist.removeDuplicates(head)
mylist.display(head);
```


<br>

## Solution


```python
class Node:
    def __init__(self,data):
        self.data = data
        self.next = None
class Solution:
    def insert(self,head,data):
            p = Node(data)           
            if head==None:
                head=p
            elif head.next==None:
                head.next=p
            else:
                start=head
                while(start.next!=None):
                    start=start.next
                start.next=p
            return head  
    def display(self,head):
        current = head
        while current:
            print(current.data,end=' ')
            current = current.next


    def removeDuplicates(self,head):
        uniques = []
        current = head
        while current:
            if current.data not in uniques:
                uniques.append(current.data)
            current = current.next
        print(*sorted(uniques))


mylist= Solution()
T=int(input())
head=None
for i in range(T):
    data=int(input())
    head=mylist.insert(head,data)    
head=mylist.removeDuplicates(head)
mylist.display(head); 
```
