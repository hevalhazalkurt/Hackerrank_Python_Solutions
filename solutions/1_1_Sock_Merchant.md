# The HackerRank Interview Preparation Kit
## 1. Warm-up Challenges

### 1.1. Sock Merchant

#### Problem
John works at a clothing store. He has a large pile of socks that he must pair by color for sale. Given an array of integers representing the color of each sock, determine how many pairs of socks with matching colors there are.

For example, there are `n=7` socks with colors `ar=[1,2,1,2,1,3,2]`. There is one pair of color `1` and one of color `2`. There are three odd socks left, one of each color. The number of pairs is `2`.


<br>

**Function Description**

Complete the `sockMerchant` function in the editor below. It must return an integer representing the number of matching pairs of socks that are available.

`sockMerchant` has the following parameter(s):
* `n`: the number of socks in the pile
* `ar`: the colors of each sock


<br>

#### Input Format

The first line contains an integer `n`, the number of socks represented in `ar`.

The second line contains `n` space-separated integers describing the colors `ar[i]` of the socks in the pile.

<br>

#### Constraints


* 1 <= `n` <= 100
* 1 <= `ar[i]` <= 100 where 0 <= `i` <= `n`

<br>

#### Output Format

Return the total number of matching pairs of socks that John can sell.

<br>

**Sample Input**

```
9
10 20 20 10 10 30 50 10 20
```

<br>

**Sample Output**

```
3
```


**Explanation**

![](https://s3.amazonaws.com/hr-challenge-images/25168/1474122392-c7b9097430-sock.png)

<br>


### Given Code

```python
import math
import os
import random
import re
import sys

# Complete the sockMerchant function below.
def sockMerchant(n, ar):

if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    n = int(input())

    ar = list(map(int, input().rstrip().split()))

    result = sockMerchant(n, ar)

    fptr.write(str(result) + '\n')

    fptr.close()

```


## Solution 1

```python
#!/bin/python3

import math
import os
import random
import re
import sys

# Complete the sockMerchant function below.
def sockMerchant(n, ar):
    return sum([v//2 for k,v in {i:ar.count(i) for i in ar}.items()])

if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    n = int(input())

    ar = list(map(int, input().rstrip().split()))

    result = sockMerchant(n, ar)

    fptr.write(str(result) + '\n')

    fptr.close()
```



## Solution 2

```python
#!/bin/python3

import math
import os
import random
import re
import sys

# Complete the sockMerchant function below.
def sockMerchant(n, ar):
    colors = {c:ar.count(c) for c in ar}
    pairs = sum([colors[c] // 2 for c in colors])
    return pairs

if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    n = int(input())

    ar = list(map(int, input().rstrip().split()))

    result = sockMerchant(n, ar)

    fptr.write(str(result) + '\n')

    fptr.close()
```



## Solution 3

```python
#!/bin/python3

import math
import os
import random
import re
import sys

# Complete the sockMerchant function below.
def sockMerchant(n, ar):
    colors = {}
    for color in ar:
        if color in colors:
            colors[color] += 1
        else:
            colors[color] = 1

    pairs = 0

    for color in colors:
        pairs += colors[color] // 2

    return pairs

if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    n = int(input())

    ar = list(map(int, input().rstrip().split()))

    result = sockMerchant(n, ar)

    fptr.write(str(result) + '\n')

    fptr.close()
```
