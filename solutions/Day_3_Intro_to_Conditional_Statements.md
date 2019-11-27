# Day 3 : Intro to Conditional Statements
## Problem
#### Objective
In this challenge, we're getting started with conditional statements.

#### Task
Given an integer, `n`, perform the following conditional actions:

If `n` is odd, print `Weird`

If `n` is even and in the inclusive range of 2 to 5, print `Not Weird`

If `n` is even and in the inclusive range of 6 to 20, print `Weird`

If `n` is even and greater than 20, print `Not Weird`

#### Input Format
A single line containing a positive integer, `n`.

#### Constraints
1 <= n <= 100

#### Output Format
Print `Weird` if the number is weird; otherwise, print `Not Weird`.

```
Sample Inputs
3
24
```

```
Sample Output
Weird
Not Weird
```

#### Explanation
Sample Case 0:  n = 3

`n` is odd and odd numbers are weird, so we print `Weird`.

Sample Case 1: n = 24

`n` and  is even, so it isn't weird. Thus, we print `Not Weird`.

#### Given Code

```python
import math
import os
import random
import re
import sys



if __name__ == '__main__':
    N = int(input())
```

## Solution 1

```python
import math
import os
import random
import re
import sys


if __name__ == '__main__':
    N = int(input())
    if N % 2 == 0 and 2 < N < 5 :
        print("Not Weird")
    elif N % 2 == 0 and 6 < N < 20 :
        print("Weird")
    elif N % 2 == 0 and N > 20 :
        print("Not Weird")
    else :
        print("Weird")
```


## Solution 2

```python
import math
import os
import random
import re
import sys



if __name__ == '__main__':
    N = int(input())
    if N % 2 != 0:
        print("Weird")
    else:
        if N <= 5:
            print("Not Weird")
        elif N <= 20:
            print("Weird")
        else:
            print("Not Weird")
```


## Solution 3

```python
import math
import os
import random
import re
import sys



if __name__ == '__main__':
    N = int(input())
    if N % 2 != 0:
        print("Weird")
    else:
        if N in range(0,6):
            print("Not Weird")
        elif N in range(6,21):
            print("Weird")
        else:
            print("Not Weird")
```


## Solution 4

```python
import math
import os
import random
import re
import sys



if __name__ == '__main__':
    N = int(input())

    def isweird(num):
        if num % 2 != 0:
            print("Weird")
        else:
            if 2 <= num <= 5:
                print("Not Weird")
            elif 6 <= num <= 20:
                print("Weird")
            else:
                print("Not Weird")
    isweird(N)
```
