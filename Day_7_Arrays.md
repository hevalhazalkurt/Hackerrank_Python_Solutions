# Day 7 : Arrays
## Problem
#### Objective
Today, we're learning about the Array data structure.

#### Task
Given an array,`A` , of `N` integers, print `A`'s elements in reverse order as a single line of space-separated numbers.

#### Input Format
The first line contains an integer, `N` (the size of our array).
The second line contains `N` space-separated integers describing array `A`'s elements

#### Constraints
1 <= N <= 1000

1 <= A<sub>i</sub> <= 10000 where A<sub>i</sub> is the i<sup>th</sup> integer in the array

#### Output Format
Print the elements of array `A` in reverse order as a single line of space-separated numbers.

```
Sample Input
4
1 4 3 2
```

```
Sample Output
2 3 4 1
```

#### Given Code

```python
import math
import os
import random
import re
import sys


if __name__ == '__main__':
    n = int(input())

    arr = list(map(int, input().rstrip().split()))
```


## Solution 1

```python
import math
import os
import random
import re
import sys


if __name__ == '__main__':
    n = int(input())

    arr = list(map(int, input().rstrip().split()))
    print(*reversed(arr))
```


## Solution 2

```python
import math
import os
import random
import re
import sys


if __name__ == '__main__':
    n = int(input())

    arr = list(map(int, input().rstrip().split()))
    print(*arr[::-1])
```



## Solution 3

```python
import math
import os
import random
import re
import sys


if __name__ == '__main__':
    n = int(input())

    arr = list(map(int, input().rstrip().split()))
    rev = list()
    for i in reversed(arr):
        rev.append(i)
    A = " ".join(str(x) for x in rev)
    print(A)
```
