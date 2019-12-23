# Day 11: 2D Arrays
## Problem
#### Objective

Today, we're building on our knowledge of Arrays by adding another dimension.

**Context**

Given a 6 X 6 2D Array, `A`:

```
1 1 1 0 0 0
0 1 0 0 0 0
1 1 1 0 0 0
0 0 0 0 0 0
0 0 0 0 0 0
0 0 0 0 0 0
```

We define an hourglass in `A`to be subset of values with indices falling in this pattern in `A`'s graphical representation :

```
a b c
  d  
e f g
```

There are 16 hourglasses in `A`, and a hourglass sum is the sum of an hourglass' values.

#### Task
Calculate the hourglass sum for every hourglass in `A`, then print the maximum hourglass sum.

#### Input Format
There are 6 lines of input, where each line contains 6 space-seperated integers describing 2D Array `A`; every value in `A` will be in the inclusive range of -9 to 9.

#### Constraints

* -9 <= `A[i][j]` <= 9
* 0 <= `i, j` <= 5


#### Output Format
Print the largest (maximum) hourglass sum found in `A`.


#### Sample Input

```
1 1 1 0 0 0
0 1 0 0 0 0
1 1 1 0 0 0
0 0 2 4 4 0
0 0 0 2 0 0
0 0 1 2 4 0
```

#### Sample Output

```
19
```

#### Explanation
`A` contains the following hourglasses:

```
1 1 1   1 1 0   1 0 0   0 0 0
  1       0       0       0
1 1 1   1 1 0   1 0 0   0 0 0

0 1 0   1 0 0   0 0 0   0 0 0
  1       1       0       0
0 0 2   0 2 4   2 4 4   4 4 0

1 1 1   1 1 0   1 0 0   0 0 0
  0       2       4       4
0 0 0   0 0 2   0 2 0   2 0 0

0 0 2   0 2 4   2 4 4   4 4 0
  0       0       2       0
0 0 1   0 1 2   1 2 4   2 4 0
```

The hourglass with the maximum sum (19) is :

```
2 4 4
  2
1 2 4
```

## Given code

```python
import math
import os
import random
import re
import sys



if __name__ == '__main__':
    arr = []

    for _ in range(6):
        arr.append(list(map(int, input().rstrip().split())))
```

## Solution 1

```python
import math
import os
import random
import re
import sys



if __name__ == '__main__':
    arr = []

    for _ in range(6):
        arr.append(list(map(int, input().rstrip().split())))

        def maxsumofhourglasses(thearray):
            sums = []

    for x in range(len(thearray)-2):
        for y in range(len(thearray)-2):
            sums.append(sum([arr[x][y],
                             arr[x][y+1],
                             arr[x][y+2],
                             arr[x+1][y+1],
                             arr[x+2][y],
                             arr[x+2][y+1],
                             arr[x+2][y+2]]))

    return max(sums)


print(maxsumofhourglasses(arr))
```

## Solution 2

```python
import math
import os
import random
import re
import sys



if __name__ == '__main__':
    arr = []

    for _ in range(6):
        arr.append(list(map(int, input().rstrip().split())))

    sums = []

    for x in range(len(arr)-2):
        for y in range(len(arr)-2):
            sums.append(sum([arr[x][y], arr[x][y+1], arr[x][y+2], arr[x+1][y+1], arr[x+2][y], arr[x+2][y+1], arr[x+2][y+2]]))

    print(max(sums))
```



## Solution 3

```python
import math
import os
import random
import re
import sys



if __name__ == '__main__':
    arr = []

    for _ in range(6):
        arr.append(list(map(int, input().rstrip().split())))

    max_sum = None

    for i in range(len(arr)-2) :
        for n in range(len(arr)-2):
            lst = [arr[i][n], arr[i][n+1], arr[i][n+2], arr[i+1][n+1], arr[i+2][n], arr[i+2][n+1], arr[i+2][n+2]]
            if max_sum == None:
                max_sum = sum(lst)
            elif sum(lst) > max_sum:
                max_sum = sum(lst)
            else:
                continue

    print(max_sum)
```
