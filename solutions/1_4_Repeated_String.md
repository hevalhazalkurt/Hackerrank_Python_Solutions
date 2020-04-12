# The HackerRank Interview Preparation Kit
## 1. Warm-up Challenges

### 1.4. Repeated String

#### Problem

Lilah has a string, `s`, of lowercase English letters that she repeated infinitely many times.

Given an integer, `n`, find and print the number of letter `a`'s in the first `n` letters of Lilah's infinite string.

For example, if the string `s = "abcac"` and `n=10`, the substring we consider is `"abcacabcac"`, the first `10` characters of her indefinite string. There are `4` occurrences of `a` in the substring.

<br>

**Function Description**

Complete the `repeatedString` function in the editor below. It should return an integer representing the number of occurrences of `a` in the prefix of length `n` in the indefinitely repeating string.

`repeatedString` has the following parameter(s):
* `s`: a string to repeat
* `n`: the number of characters to consider

<br>

#### Input Format

The first line contains a single string, `s`.

The second line contains an integer, `n`.

<br>

#### Constraints

* 1 <= |`s`| <= 100
* 1 <= `n` <= 10<sup>6</sup>
* For 25% of the test cases, `n` <= 10<sup>6</sup>


<br>

#### Output Format

Print
a single integer denoting the number of letter `a`'s in the first `n` letters of the infinite string created by repeating `s` infinitely many times.

<br>

**Sample Input 0**

```
aba
10
```

<br>

**Sample Output 0**

```
7
```


**Explanation 0**

The first `n=10` letters of the infinite string are `abaabaabaa`. Because there are `7` `a`'s, we print `7` on a new line.



<br>

**Sample Input 1**

```
a
1000000000000
```

<br>

**Sample Output 1**

```
1000000000000
```


**Explanation 1**

Because all of the first `n = 1000000000000` letters of the infinite string are `a`, we print `1000000000000` on a new line.



<br>


### Given Code

```python
import math
import os
import random
import re
import sys

# Complete the repeatedString function below.
def repeatedString(s, n):

if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    s = input()

    n = int(input())

    result = repeatedString(s, n)

    fptr.write(str(result) + '\n')

    fptr.close()
```


## Solution

```python
import math
import os
import random
import re
import sys

# Complete the repeatedString function below.
def repeatedString(s, n):
    a_s = s.count("a")
    return (a_s * (n // len(s))) + s[:n%len(s)].count("a")  if "a" in s else 0


if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    s = input()

    n = int(input())

    result = repeatedString(s, n)

    fptr.write(str(result) + '\n')

    fptr.close()
```
