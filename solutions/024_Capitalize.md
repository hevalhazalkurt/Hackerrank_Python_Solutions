# 024 - Capitalize

## Problem

You are asked to ensure that the first and last names of people begin with a capital letter in their passports. For example, `alison heck` should be capitalized correctly as `Alison Heck`.

Given a full name, your task is to capitalize the name appropriately.


<br>

### Input Format

A single line of input containing the full name, `S`.


### Constraints


* 0 < `len(S)` < 1000
* The string consists of alphanumeric characters and spaces.

Note: in a word only the first character is capitalized. Example 12abc when capitalized remains 12abc.



### Output Format

Print the capitalized string, `S`.

<br>

**Sample Input**

```
chris alan
```

<br>

**Sample Output**

```
Chris Alan
```



<br>


### Given Code

```python
# Complete the solve function below.
def solve(s):

if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    s = input()

    result = solve(s)

    fptr.write(result + '\n')

    fptr.close()
```


## Solution

```python
# Complete the solve function below.
def solve(s):
    return ' '.join((word.capitalize() for word in s.split(' ')))


if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    s = input()

    result = solve(s)

    fptr.write(result + '\n')

    fptr.close()
```
