# The HackerRank Interview Preparation Kit
## 3. Dictionaries and Hashmaps

### 3.4. Count Triplets

#### Problem

You are given an array and you need to find number of triplets of indices `(i,j,k)` such that the elements at those indices are in [geometric progression](https://en.wikipedia.org/wiki/Geometric_progression) for a given common ratio `r` and `i < j < k`.

For example, `arr = [1,4,16,64]`. If `r=4`, we have `[1,4,16]` at indices `(0,1,2)` and `(1,2,3)`.

<br>

**Function Description**

Complete the `countTriplets` function in the editor below. It should return the number of triplets forming a geometric progression for a given `r` as an integer.

`countTriplets` has the following parameter(s):
* `arr` : an array of integers
* `r` : an array of integers


<br>

#### Input Format

The first line contains two space-separated integers `n` and `r`, the size of `arr` and the common ratio.

The next line contains `n` space-seperated integers `arr[i]`.


<br>

#### Constraints

* 1 <= `n` <= 10<sup>5</sup>
* 1 <= `r` <= 10<sup>9</sup>
* 1 <= `arr[i]` <= 10<sup>9</sup>


<br>

#### Output Format

Return the count of triplets that form a geometric progression.

<br>

**Sample Input 0**

```
4 2
1 2 2 4
```

<br>

**Sample Output 0**

```
2
```


<br>

**Explanation 0**


There are `2` triplets in satisfying our criteria, whose indices are `(0,1,3)` and `(0,2,3)`

<br>


**Sample Input 1**

```
6 3
1 3 9 9 27 81
```

<br>

**Sample Output 1**

```
6
```


<br>

**Explanation 1**


The triplets satisfying are index `(0,1,2)`, `(0,1,3)`, `(1,2,4)`, `(1,3,4)`, `(2,4,5)` and `(3,4,5)`


<br>


**Sample Input 2**

```
5 5
1 5 5 25 125
```

<br>

**Sample Output 2**

```
4
```


<br>

**Explanation 2**

The triplets satisfying are index `(0,1,3)`, `(0,2,3)`, `(1,3,4)`, `(2,3,4)`



<br>


### Given Code

```python
import math
import os
import random
import re
import sys

# Complete the countTriplets function below.
def countTriplets(arr, r):

if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    nr = input().rstrip().split()

    n = int(nr[0])

    r = int(nr[1])

    arr = list(map(int, input().rstrip().split()))

    ans = countTriplets(arr, r)

    fptr.write(str(ans) + '\n')

    fptr.close()
```


## Solution 1

```python
import math
import os
import random
import re
import sys
from collections import defaultdict

# Complete the countTriplets function below.
def countTriplets(arr, r):
    d1 = defaultdict(int)
    d2 = defaultdict(int)
    c = 0

    for i in reversed(arr):
        if i*r in d2:
            c += d2[i*r]
        if i*r in d1:
            d2[i] += d1[i*r]
        d1[i]+=1

    return c

if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    nr = input().rstrip().split()

    n = int(nr[0])

    r = int(nr[1])

    arr = list(map(int, input().rstrip().split()))

    ans = countTriplets(arr, r)

    fptr.write(str(ans) + '\n')

    fptr.close()
```




## Solution 2

```python
import math
import os
import random
import re
import sys
from collections import defaultdict

# Complete the countTriplets function below.
def countTriplets(arr, r):
    c = 0
    i = 0

    while i < len(arr) - 2:
        j = i + 1
        k = i + 2

        while j < len(arr) - 1:
            if arr[i] * r == arr[j] and arr[j] * r == arr[k]:
                print(arr[i], arr[j], arr[k])
                c += 1

            if k == len(arr) - 1:
                j += 1
                k = j + 1
            else:
                k += 1
        i += 1

    return c

    

if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    nr = input().rstrip().split()

    n = int(nr[0])

    r = int(nr[1])

    arr = list(map(int, input().rstrip().split()))

    ans = countTriplets(arr, r)

    fptr.write(str(ans) + '\n')

    fptr.close()
```
