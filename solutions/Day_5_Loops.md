# Day 5: Loops
## Problem
#### Objective
In this challenge, we're going to use loops to help us do some simple math.

#### Task
Given an integer,`n` , print its first 10 multiples. Each multiple `n x i` (where 1 <= i <= 10 ) should be printed on a new line in the form: n x i = result.

#### Input Format
A single integer, `n` .

#### Constraints
2 <= n <= 20

#### Output Format
Print 10 lines of output; each line `i` (where 1 <= i <= 10 ) contains the `result` of `n x i` in the form:
n x i = result.

```
-- Sample Input --
2
```

```
-- Sample Output --
2 x 1 = 2
2 x 2 = 4
2 x 3 = 6
2 x 4 = 8
2 x 5 = 10
2 x 6 = 12
2 x 7 = 14
2 x 8 = 16
2 x 9 = 18
2 x 10 = 20
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
    numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

    for i in numbers :
        print(n, "x", i, "=", (n*i))
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

    for i in range(1,11):
        result = n * i
        print("{} x {} = {}".format(n, i, result))
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

    for i in range(1,11):
        print("{} x {} = {}".format(n, i, n * i))
```


## Solution 4

```python
import math
import os
import random
import re
import sys



if __name__ == '__main__':
    n = int(input())

    def ten_multiple(n):
        for num in range(1,11):
            print("{} x {} = {}".format(n,num,n*num))

    ten_multiple(n)
```
