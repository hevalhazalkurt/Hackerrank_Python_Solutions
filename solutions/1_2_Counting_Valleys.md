# The HackerRank Interview Preparation Kit
## 1. Warm-up Challenges

### 1.2. Counting Valleys

#### Problem

Gary is an avid hiker. He tracks his hikes meticulously, paying close attention to small details like topography. During his last hike he took exactly `n` steps. For every step he took, he noted if it was an uphill, `U`, or a downhill, `D` step. Gary's hikes start and end at sea level and each step up or down represents a `1` unit change in altitude. We define following terms :

* A mountain is a sequence of consecutive steps above sea level, starting with a step up from sea level and ending with a step down to sea level.
* A valley is a sequence of consecutive steps below sea level, starting with a step down from sea level and ending with a step up to sea level.

Given Gary's sequence of up and down steps during his last hike, find and print the number of valleys he walked through.

For example, if Gary's path is `s = [DDUUUUDD]`, he first enters a valley `2` units deep. Then he climbs out an up onto a mountain `2` units high. Finally, he returns to sea level and ends his hike.

<br>

**Function Description**

Complete the `countingValley` function in the editor below. It must return an integer that denotes of valleys Gary traversed.

`countingValley` has the following parameter(s):
* `n`: the number of steps Gary takes
* `s`: a string describing his path

<br>

#### Input Format

The first line contains an integer `n`, the number of steps in Gary's hike.

The second line contains a single string `s`, of `n` characters that describe his path.

<br>

#### Constraints


* 2 <= `n` <= 10<sup>6</sup>
* `s[i]` ∈ `{UD}`

<br>

#### Output Format

Print a single integer that denotes the number of valleys Gary walked through during his hike.

<br>

**Sample Input**

```
8
UDDDUDUU
```

<br>

**Sample Output**

```
1
```


**Explanation**

If we represent `_` as sea level, a step up as `/`, and a step down as `\`, Gary's hike can be drawn as :

```
_/\      _
   \    /
    \/\/
```


He enters and leaves one valley.


<br>


### Given Code

```python

import math
import os
import random
import re
import sys

# Complete the countingValleys function below.
def countingValleys(n, s):

if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    n = int(input())

    s = input()

    result = countingValleys(n, s)

    fptr.write(str(result) + '\n')

    fptr.close()

```


## Solution 1

```python
import math
import os
import random
import re
import sys

def countingValleys(n, s):
    a = 0
    v = 0

    for i in s:
        if i == "U":
            a += 1
            if a == 0:
                v += 1
        else:
            a -= 1

    return v


if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    n = int(input())

    s = input()

    result = countingValleys(n, s)

    fptr.write(str(result) + '\n')

    fptr.close()
```

<br>


## Solution 2

```python
import math
import os
import random
import re
import sys

def countingValleys(n, s):
    a = 0
    l = [0]
    v = 0

    for i in range(n):
        if s[i] == "U":
            a += 1
        else:
            a -= 1
        l.append(a)

    for i,s in enumerate(l):
        if l[i-1] < 0 and s == 0:
            v += 1
    return v


if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    n = int(input())

    s = input()

    result = countingValleys(n, s)

    fptr.write(str(result) + '\n')

    fptr.close()
```
