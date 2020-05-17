# Day 28 : RegEx, Patterns, and Intro to Databases
## Problem
#### Objective

Today, we're working with regular expressions.

<br>

#### Task

Consider a database table, Emails, which has the attributes First Name and Email ID. Given `N` rows of data simulating the Emails table, print an alphabetically-ordered list of people whose email address ends in `@gmail.com`.

<br>

#### Input Format

The first line contains an integer, `N`, total number of rows in the table.

Each of the `N` subsequent lines contains `2` space-separated strings denoting a person's first name and email ID, respectively.

<br>

#### Constraints

* 2 ≤ `N` ≤ 30
* Each of the first names consists of lower case letters `[a - z]` only.
* Each of the email IDs consists of lower case letters `[a - z]`, `@` and `.` only.
* The lenght of the first name is no longer than 20.
* The lenght of the email ID is no longer than 50.


<br>

#### Output Format

Print an alphabetically-ordered list of first names for every user with a gmail account. Each name must be printed on a new line.

<br>

#### Sample Input


```
6
riya riya@gmail.com
julia julia@julia.me
julia sjulia@gmail.com
julia julia@gmail.com
samantha samantha@gmail.com
tanya tanya@gmail.com
```

<br>

#### Sample Output


```
julia
julia
riya
samantha
tanya
```

<br>



## Given code

```python
#!/bin/python3

import math
import os
import random
import re
import sys



if __name__ == '__main__':
    N = int(input())

    for N_itr in range(N):
        firstNameEmailID = input().split()

        firstName = firstNameEmailID[0]

        emailID = firstNameEmailID[1]
```


<br>

## Solution 1


```python
import math
import os
import random
import re
import sys



if __name__ == '__main__':
    N = int(input())
    table = []

    for N_itr in range(N):
        firstNameEmailID = input().split()

        firstName = firstNameEmailID[0]

        emailID = firstNameEmailID[1]

        if firstName.isalpha() and "@gmail.com" in emailID:
            table.append(firstName)

    print("\n".join(sorted(table)))
```

<br>

## Solution 2


```python
import math
import os
import random
import re
import sys



if __name__ == '__main__':
    N = int(input())
    table = []

    for N_itr in range(N):
        firstNameEmailID = input().split()

        firstName = firstNameEmailID[0]

        emailID = firstNameEmailID[1]

        if re.search(".+@gmail\.com$", emailID):
            table.append(firstName)

    table.sort()

    print(*table, sep="\n")
```
