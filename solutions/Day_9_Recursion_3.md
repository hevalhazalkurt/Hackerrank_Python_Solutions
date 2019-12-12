# Day 9: Recursion 3
## Problem
#### Objective
Today, we're learning and practicing an algorithmic concept called Recursion.

**Recursive Method for Calculating Factorial**

![](http://i65.tinypic.com/iefc3t.png)

#### Task
Write a factorial function that takes a positive integer, `N` as a parameter and prints the result of `N!` (`N` factorial).

**Note**: If you fail to use recursion or fail to name your recursive function factorial or Factorial, you will get a score of `0`

#### Input Format
A single integer, `N` (the argument to pass to factorial).

#### Constraints
2 <= N <= 12

Your submission must contain a recursive function named factorial.

#### Output Format
On a new line for each query, print `Not found` if the name has no corresponding entry in the phone book; otherwise, print the full `name` and `phoneNumber` in the format `name=phoneNumber`.


#### Sample Input

```
3
```

#### Sample Output

```
6
```

#### Explanation
Consider the following steps:

1. factorial(3) = 3 x factorial(2)
2. factorial(2) = 2 x factorial(1)
3. factorial(1) = 1

From steps 2 and 3, we can say factorial(2) = 2 x 1 = 2; then when we apply the value from factorial(2) to step 1, we get factorial(3) = 3 x 2 x 1 = 6. Thus, we print 6 as our answer.


## Given code

```python
import math
import os
import random
import re
import sys

# Complete the factorial function below.
def factorial(n):

if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    n = int(input())

    result = factorial(n)

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

# Complete the factorial function below.
def factorial(n):
    if n == 1:
        return 1
    else:
        n_fact = n * factorial(n - 1)
        return n_fact

if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    n = int(input())

    result = factorial(n)

    fptr.write(str(result) + '\n')

    fptr.close()
```


## Solution 2

```python
import math
import os
import random
import re
import sys

# Complete the factorial function below.
def factorial(n):
    return 1 if n == 1 else n * factorial(n-1)

if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    n = int(input())

    result = factorial(n)

    fptr.write(str(result) + '\n')

    fptr.close()
```
