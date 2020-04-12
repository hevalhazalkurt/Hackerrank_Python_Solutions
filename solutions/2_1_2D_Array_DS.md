# The HackerRank Interview Preparation Kit
## 2. Arrays

### 2.1. 2D Array - DS

#### Problem

Given a 6 x 6 2D Array, `arr`:

```
1 1 1 0 0 0
0 1 0 0 0 0
1 1 1 0 0 0
0 0 0 0 0 0
0 0 0 0 0 0
0 0 0 0 0 0
```

We define an hourglass in `A` to be a subset of values with indices falling in this pattern in `arr`'s graphical representation:

```
a b c
  d
e f g
```


There are 16 hourglasses in `arr`, and an hourglass sum is the sum of an hourglass' values. Calculate the hourglass sum for every hourglass in `arr`, then print the maximum hourglass sum.

For example, given the 2D array:


```
-9 -9 -9  1 1 1
 0 -9  0  4 3 2
-9 -9 -9  1 2 3
 0  0  8  6 6 0
 0  0  0 -2 0 0
 0  0  1  2 4 0
```


We calculate the following 16 hourglass values:

```
-63, -34, -9, 12,
-10, 0, 28, 23,
-27, -11, -2, 10,
9, 17, 25, 18
```

Our highest hourglass value is 28 from the hourglass:


```
0 4 3
  1
8 6 6
```

Note: If you have already solved the Java domain's Java 2D Array challenge, you may wish to skip this challenge.


<br>

**Function Description**

Complete the function `hourglassSum` in the editor below. It should return an integer, the maximum hourglass sum in the array.

`hourglassSum` has the following parameter(s):
* `arr`: an array of integers

<br>

#### Input Format

Each of the 6 lines of inputs `arr[i]` contains 6 space-separated integers `arr[i][j]`.

<br>

#### Constraints

* -9 <= `arr[i][j]` <= 9
* 0 <= `i,j` <= 5



<br>

#### Output Format

Print the largest (maximum) hourglass sum found in `arr`.

<br>

**Sample Input 0**

```
1 1 1 0 0 0
0 1 0 0 0 0
1 1 1 0 0 0
0 0 2 4 4 0
0 0 0 2 0 0
0 0 1 2 4 0
```

<br>

**Sample Output 0**

```
19
```


**Explanation 0**

`arr` contains the following hourglasses:

![](https://s3.amazonaws.com/hr-assets/0/1534256743-35b846ad4a-hourglasssum.png)


The hourglass with the maximum sum(19) is:

```
2 4 4
  2
1 2 4
```

<br>

<br>


### Given Code

```python
#!/bin/python3

import math
import os
import random
import re
import sys

# Complete the hourglassSum function below.
def hourglassSum(arr):


if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    arr = []

    for _ in range(6):
        arr.append(list(map(int, input().rstrip().split())))

    result = hourglassSum(arr)

    fptr.write(str(result) + '\n')

    fptr.close()

```


## Solution

```python
#!/bin/python3

import math
import os
import random
import re
import sys

# Complete the hourglassSum function below.
def hourglassSum(arr):
    sums = []

    for c in range(4):
        for r in range(4):
            sums.append(sum(arr[c][r:r+3]) + arr[c+1][r+1] + sum(arr[c+2][r:r+3]))

    return max(sums)


if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    arr = []

    for _ in range(6):
        arr.append(list(map(int, input().rstrip().split())))

    result = hourglassSum(arr)

    fptr.write(str(result) + '\n')

    fptr.close()

```
