# 014 - sWAP cASE
## Problem

You are given a string and your task is to swap cases. In other words, convert all lowercase letters to uppercase letters and vice versa.

**For Example**

```
Www.HackerRank.com → wWW.hACKERrANK.COM
Pythonist 2 → pYTHONIST 2
```


### Input Format

A single line containing a string `S`.


### Constraints

0 < `len(S)` <= 1000


### Output Format

Print the modified string `S`.


**Sample Input 0**

```
HackerRank.com presents "Pythonist 2".
```

**Sample Output 0**

```
hACKERrANK.COM PRESENTS "pYTHONIST 2".
```


<br>


### Given Code

```python
def swap_case(s):
    return

if __name__ == '__main__':
    s = input()
    result = swap_case(s)
    print(result)
```


## Solution 1

```python
def swap_case(s):
    return s.swapcase()

if __name__ == '__main__':
    s = input()
    result = swap_case(s)
    print(result)
```


## Solution 2

```python
def swap_case(s):
    swapped = ""

    for c in s:
        if c.islower():
            swapped = swapped + c.upper()
        elif c.isupper():
            swapped = swapped + c.lower()
        else:
            swapped = swapped + c

    return swapped

if __name__ == '__main__':
    s = input()
    result = swap_case(s)
    print(result)
```
