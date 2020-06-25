# The HackerRank Interview Preparation Kit
## 3. Dictionaries and Hashmaps

### 3.2. Two Strings

#### Problem

Given two strings, determine if they share a common substring. A substring may be as small as one character. For example, the words "a", "and", "art" share the common substring `a`. The words "be" and "cat" do not share a substring.

<br>

**Function Description**

Complete the function `twoStrings` in the editor below. It should return a string, either `YES` or `NO` based on whether the strings share a common substring.

`twoStrings` has the following parameter(s):
* `s1`, `s2`: two strings to analyze.

<br>

#### Input Format

The first line contains a single integer `p`, the number of test cases.

The following `p` pairs of lines are as follows:
* The first line contains string `s1`.
* The second line contains string `s2`

<br>

#### Constraints

* `s1` and `s2` consist of characters in the range ascii[a-z].
* 1 <= `p` <= 10
* 1 <= `|s1|`, `|s2|` <= 10<sup>5</sup>


<br>

#### Output Format

For each pair of strings, return `YES` or `NO`.

<br>

**Sample Input**

```
2
hello
world
hi
world
```

<br>

**Sample Output**

```
YES
NO
```


<br>

**Explanation**


We have `p = 2` pairs to check:

1. `s1 = "hello"`, `s2 = "world"`. The substrings `"o"` and `"l"` are common to both strings.
2. `a = "hi"`, `b = "world"`. `s1` and `s2` share no common substrings.


<br>





### Given Code

```python
import math
import os
import random
import re
import sys

# Complete the twoStrings function below.
def twoStrings(s1, s2):

if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    q = int(input())

    for q_itr in range(q):
        s1 = input()

        s2 = input()

        result = twoStrings(s1, s2)

        fptr.write(result + '\n')

    fptr.close()
```


## Solution 1

```python
import math
import os
import random
import re
import sys


def twoStrings(s1, s2):
    for w in s1:
        if w in s2:
            return "YES"
    else:
        return "NO"


if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    q = int(input())

    for q_itr in range(q):
        s1 = input()

        s2 = input()

        result = twoStrings(s1, s2)

        fptr.write(result + '\n')

    fptr.close()
```



## Solution 2

```python
import math
import os
import random
import re
import sys


def twoStrings(s1, s2):
    if len(set(s1).intersection(set(s2))) >= 1:
        return "YES"
    else:
        return "NO"


if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    q = int(input())

    for q_itr in range(q):
        s1 = input()

        s2 = input()

        result = twoStrings(s1, s2)

        fptr.write(result + '\n')

    fptr.close()
```
