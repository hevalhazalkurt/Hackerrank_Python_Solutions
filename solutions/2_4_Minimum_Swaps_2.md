# The HackerRank Interview Preparation Kit
## 2. Arrays

### 2.4. Minimum Swaps 2

#### Problem

You are given an unordered array consisting of consecutive integers [1, 2, 3, ..., n] without any duplicates. You are allowed to swap any two elements. You need to find the minimum number of swaps required to sort the array in ascending order.

For example, given the array `arr = [7,1,3,2,4,5,6]` we perform the following steps:

```
i   arr                     swap (indices)
0   [7, 1, 3, 2, 4, 5, 6]   swap (0,3)
1   [2, 1, 3, 7, 4, 5, 6]   swap (0,1)
2   [1, 2, 3, 7, 4, 5, 6]   swap (3,4)
3   [1, 2, 3, 4, 7, 5, 6]   swap (4,5)
4   [1, 2, 3, 4, 5, 7, 6]   swap (5,6)
5   [1, 2, 3, 4, 5, 6, 7]
```

It took 5 swaps to sort the array.

<br>

**Function Description**

Complete the function `minimumSwaps` in the editor below. It must return an integer representing the minimum number of swaps to sort the array.

`minimumSwaps` has the following parameter(s):

* `arr`: an unordered array of integers

<br>

#### Input Format

The first line contains an integer, `n` , the size of `arr`.
The second line contains `n` space-separated integers `arr[i]`.

<br>

#### Constraints

* 1 ≤ `n` ≤ 10<sup>5</sup>
* 1 ≤ `arr[i]` ≤ `n`


<br>


#### Output Format

Return the minimum number of swaps to sort the given array.

<br>

**Sample Input 0**

```
4
4 3 1 2
```

<br>

**Sample Output 0**

```
3
```


**Explanation 0**

Given array `arr : [4,3,1,2]` <br>
After swapping `(0,2)` we get `arr : [1,3,4,2]` <br>
After swapping `(1,2)` we get `arr : [1,4,3,2]` <br>
After swapping `(1,3)` we get `arr : [1,2,3,4]` <br>
So, we need a minimum of 3 swaps to sort the array in ascending order.

<br>



**Sample Input 1**

```
5
2 3 4 1 5
```

<br>

**Sample Output 1**

```
3
```


**Explanation 1**

Given array `arr : [2,3,4,1,5]` <br>
After swapping `(2,3)` we get `arr : [2,3,1,4,5]` <br>
After swapping `(0,1)` we get `arr : [3,2,1,4,5]` <br>
After swapping `(0,2)` we get `arr : [1,2,3,4,5]` <br>
So, we need a minimum of 3 swaps to sort the array in ascending order.

<br>


**Sample Input 2**

```
7
1 3 5 2 4 6 7
```

<br>

**Sample Output 2**

```
3
```


**Explanation 2**

Given array `arr : [1,3,5,2,4,6,7` <br>
After swapping `(1,3)` we get `arr : [1,2,5,3,4,6,7]` <br>
After swapping `(2,3)` we get `arr : [1,2,3,5,4,6,7]` <br>
After swapping `(3,4)` we get `arr : [1,2,3,4,5,6,7]` <br>
So, we need a minimum of 3 swaps to sort the array in ascending order.

<br>



### Given Code

```python
import math
import os
import random
import re
import sys

# Complete the minimumSwaps function below.
def minimumSwaps(arr):



if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    n = int(input())

    arr = list(map(int, input().rstrip().split()))

    res = minimumSwaps(arr)

    fptr.write(str(res) + '\n')

    fptr.close()
```


## Solution

```python
import math
import os
import random
import re
import sys

# Complete the minimumSwaps function below.
def minimumSwaps(arr):
    swaps = 0

    for i in range(0, n - 1):
        while arr[i] != i + 1:
            temp = arr[arr[i] - 1]
            arr[arr[i] - 1] = arr[i]
            arr[i] = temp
            swaps += 1
    return swaps



if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    n = int(input())

    arr = list(map(int, input().rstrip().split()))

    res = minimumSwaps(arr)

    fptr.write(str(res) + '\n')

    fptr.close()
```
