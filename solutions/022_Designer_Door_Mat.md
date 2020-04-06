# 022 - Designer Door Mat

## Problem

Mr. Vincent works in a door mat manufacturing company. One day, he designed a new door mat with the following specifications.

* Mat size must be `N` x `M`. (`N` is an odd natural number, and `M` is times `N`.)
* The design should have "WELCOME" written in the center.
* The design pattern should only use `|,.` and `-` characters.


<br>

### Sample Design

```
Size: 7 x 21
---------.|.---------
------.|..|..|.------
---.|..|..|..|..|.---
-------WELCOME-------
---.|..|..|..|..|.---
------.|..|..|.------
---------.|.---------

Size: 11 x 33
---------------.|.---------------
------------.|..|..|.------------
---------.|..|..|..|..|.---------
------.|..|..|..|..|..|..|.------
---.|..|..|..|..|..|..|..|..|.---
-------------WELCOME-------------
---.|..|..|..|..|..|..|..|..|.---
------.|..|..|..|..|..|..|.------
---------.|..|..|..|..|.---------
------------.|..|..|.------------
---------------.|.---------------
```

<br>

### Input Format

A single line containing the space separated values of `N` and `M`.

<br>


### Constraints


5 < `N` < 101 <br>
15 < `M` < 303


<br>

### Output Format

Output the design pattern.

<br>

**Sample Input**

```
9 27
```

<br>

**Sample Output**

```
------------.|.------------
---------.|..|..|.---------
------.|..|..|..|..|.------
---.|..|..|..|..|..|..|.---
----------WELCOME----------
---.|..|..|..|..|..|..|.---
------.|..|..|..|..|.------
---------.|..|..|.---------
------------.|.------------
```



<br>


### Given Code

```python
# Enter your code here. Read input from STDIN. Print output to STDOUT
```


## Solution

```python
user_input = input().split()

n,m = int(user_input[0]), int(user_input[1])

s = 1

for line in range(n+1):
    if line < int(n/2):
        print((".|."*s).center(m, "-"))
        s += 2
    elif line == round(n/2):
        print("WELCOME".center(m, "-"))
    elif line > int(n/2) and s > 1:
        s -= 2
        print((".|."*s).center(m, "-"))
```
