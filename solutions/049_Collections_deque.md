# 049 - Collections.deque()


## Problem

[Collections.deque()](https://docs.python.org/2/library/collections.html#collections.deque)


A deque is a double-ended queue. It can be used to add or remove elements from both ends.

Deques support thread safe, memory efficient appends and pops from either side of the deque with approximately the same `O(1)` performance in either direction.

Click on the link to learn more about **deque() methods**.

Click on the link to learn more about various approaches to working with deques : **Deque Recipes**.


<br>

**Example**

```python
from collections import deque

d = deque()
d.append(1)
print(d)

d.appendleft(2)
print(d)

d.clear()
print(d)

d.extend("1")
print(d)

d.extendleft("234")
print(d)

print(d.count("1"))

print(d.pop())

print(d)

print(d.popleft())

print(d)

d.extend("7896")
print(d)

d.remove("2")
print(d)

d.reverse()
print(d)

d.rotate(3)
print(d)
```

<br>

### Constraints


Perform `append`, `pop`, `popleft` and `appendleft` methods on an empty degue `d`

<br>


### Input Format

The first line contains an integer `N`, the number of operations.

The next `N` lines contains the space separated names of methods an their values.

<br>

### Constraints


1 < `N` <= 100



<br>



### Output Format

Print the space separated elements of deque `d`.

<br>



**Sample Input**



```
6
append 1
append 2
append 3
appendleft 4
pop
popleft
```

<br>


**Sample Output**


```
1 2
```


<br>


## Solution

```python
from collections import deque

def eval_d(N):
    d = deque()

    for i in range(N):
        user = input().split()
        if len(user) > 1:
            m, e = user[0], user[1]
        else:
            m = user[0]

        if m == "append":
            d.append(e)
        elif m == "appendleft":
            d.appendleft(e)
        elif m == "pop":
            d.pop()
        elif m == "popleft":
            d.popleft()

    return " ".join([i for i in d])

print(eval_d(int(input())))
```
