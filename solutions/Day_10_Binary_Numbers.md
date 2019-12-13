# Day 10: Binary Numbers
## Problem
#### Objective

Today, we're working with binary numbers.

#### Task
Given a base-`10` integer,`n` , convert it to binary (base-`2`). Then find and print the base-`10` integer denoting the maximum number of consecutive `1`'s in `n`'s binary representation.

#### Input Format
A single integer, `n`.

#### Constraints
1 <= N <= 10<sup>6</sup>

Your submission must contain a recursive function named factorial.

#### Output Format
Print a single base-`10` integer denoting the maximum number of consecutive `1`'s in the binary representation of `n`.


#### Sample Input 1

```
5
```

#### Sample Output 1

```
1
```

#### Sample Input 2

```
13
```

#### Sample Output 2

```
2
```

#### Explanation
Sample Case 1:
The binary representation of `5` is `101`, so the maximum number of consecutive `1`'s is `1`.

Sample Case 2:
The binary representation of `13` is `1101`, so the maximum number of consecutive `1`'s is `2`.


## Given code

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

    def ones(n):
        bin_n = ""

        while n != 0:
            bin_n = str(n % 2) + bin_n
            n = n // 2

        mx = max([len(i) for i in bin_n.split("0")])
        return mx

    print(ones(n))
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
    bin_num = ""

    while n != 0:
        r = n // 2
        remainder = n - 2 * r
        bin_num = str(remainder) + bin_num
        n = r

    slice = bin_num.split("0")

    con = None
    for i in slice:
        if con == None:
            con = len(i)
        else:
            if len(i) > con :
                con = len(i)
            else :
                continue
    print(con)
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
    remainder = []

    while n >= 1 :
        r = n % 2
        remainder.append(int(r))
        n = n / 2

    rev = remainder[::-1]
    bin_num = "".join(str(x) for x in rev)

    slice = bin_num.split("0")

    con = None
    for i in slice:
        if con == None:
            con = len(i)
        else:
            if len(i) > con :
                con = len(i)
            else :
                continue
    print(con)
```
