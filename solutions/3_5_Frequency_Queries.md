# The HackerRank Interview Preparation Kit
## 3. Dictionaries and Hashmaps

### 3.5. Frequency Queries

#### Problem

You are given `q` queries. Each query is of the form two integers described below:
* 1 `x` : Insert x in your data structure.
* 2 `y` : Delete one occurence of y from your data structure, if present.
* 3 `z` : Check if any integer is present whose frequency is exactly `z`. If yes, print 1 else 0.

The queries are given in the form of a 2-D array `querries` of sizes `q` where `queries[i][0]` contains the operation, and `queries[i][1]` contains the data element. For example, you are given array

`queries = [(1,1),(2,2),(3,2),(1,1),(1,1),(2,1),(3,2)]`

The results of each operation are :


```
Operation   Array   Output
(1,1)       [1]
(2,2)       [1]
(3,2)                   0
(1,1)       [1,1]
(1,1)       [1,1,1]
(2,1)       [1,1]
(3,2)                   1
```

Return an array with the output : `[0,1]`

<br>

**Function Description**

Complete the `freqQuery` function in the editor below. It must return an array of integers where each element is a `1` if there at least one element value with the queried number of occurrences in the current array, or `0` if there is not.

`freqQeury` has the following parameter(s):
- queries : a 2-d array of integers


<br>

#### Input Format

The first line contains of an integer `q`, the number of queries.

Each of the next `q` lines contains two integers denoting the 2-d array `queries`.

<br>

#### Constraints

* 1 <= `q` <= 10<sup>5</sup>
* 1 <= `x,y,z` <= 10<sup>9</sup>
* All `queries[i][0] ∈ {1,2,3}`
* 1 <= `queries[i][0]` <= 10<sup>9</sup>


<br>

#### Output Format

Return an integer array consisting of all the outputs of queries of type `3`.

<br>
<br>


**Sample Input 0**

```
8
1 5
1 6
3 2
1 10
1 10
1 6
2 5
3 2
```

<br>

**Sample Output 0**

```
0
1
```


<br>

**Explanation 0**

For the first query of type `3`, there is no integer whose frequency is `2(array = [5,6])`. So answer is `0`.

For the second query of type `3`, there are two integers in `array = [6,10,10,6]` whose frequenct is `2`(integers = `6` and `10`). So the answer is `1`.


<br>


**Sample Input 1**

```
4
3 4
2 1003
1 16
3 1
```

<br>

**Sample Output 1**

```
0
1
```


<br>

**Explanation 1**

For the first query of tyupe `3`, there is no integer of frequency `4`. The answer is `0`. For the second query of type `3`, there is one integer, `16` of frequency `1` so the answer is `1`.


<br>


**Sample Input 2**

```
10
1 3
2 3
3 2
1 4
1 5
1 5
1 4
3 2
2 4
3 2
```

<br>

**Sample Output 2**

```
0
1
1
```


<br>

**Explanation 2**


When the first output query is run, the array is empty. We insert two `4`'s and two `5`'s before the second output query, `arr = [4,5,5,4]` so there are two instances of elements occurring twice. We delete a `4` and run the same query. Now only the instances of `5` satisfy the query.


<br>


### Given Code

```python
import math
import os
import random
import re
import sys

# Complete the freqQuery function below.
def freqQuery(queries):

if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    q = int(input().strip())

    queries = []

    for _ in range(q):
        queries.append(list(map(int, input().rstrip().split())))

    ans = freqQuery(queries)

    fptr.write('\n'.join(map(str, ans)))
    fptr.write('\n')

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
from collections import Counter

# Complete the freqQuery function below.
def freqQuery(queries):
    freq = Counter()
    cnt = Counter()
    result = []
    for action, value in queries:
        if action == 1:
            cnt[ freq[value] ] -= 1
            freq[value] += 1
            cnt[ freq[value] ] += 1
        elif action == 2:
            if freq[value] > 0:
                cnt[ freq[value] ] -= 1
                freq[value] -= 1
                cnt[ freq[value] ] += 1
        else:
            result.append(1 if cnt[value] > 0 else 0)
    return result



if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    q = int(input().strip())

    queries = []

    for _ in range(q):
        queries.append(list(map(int, input().rstrip().split())))

    ans = freqQuery(queries)

    fptr.write('\n'.join(map(str, ans)))
    fptr.write('\n')

    fptr.close()
```
