# 031 - itertools.permutations()

## Problem

[itertools.permutations()](https://docs.python.org/2/library/itertools.html#itertools.permutations)

This tool returns successive `r` length permutations of elements in an iterable.

If `r` is not specified or is `None`, then `r` defaults to the length of the iterable, and all possible full length permutatons are generated.

Permutations are printed in a lexicographic sorted order. So, if the input iterable is sorted, the permutation tuples will be produced in a sorted order.

**Sample Code**

```python
from itertools import permutations

print(permutations(["1", "2", "3"]))
print(list(permutations(["1", "2", "3"])))
print(list(permutations(["1", "2", "3"], 2)))
print(list(permutations("abc", 3)))
```

```
<itertools.permutations object at 0x10c3e88f0>
[('1', '2', '3'), ('1', '3', '2'), ('2', '1', '3'), ('2', '3', '1'), ('3', '1', '2'), ('3', '2', '1')]
[('1', '2'), ('1', '3'), ('2', '1'), ('2', '3'), ('3', '1'), ('3', '2')]
[('a', 'b', 'c'), ('a', 'c', 'b'), ('b', 'a', 'c'), ('b', 'c', 'a'), ('c', 'a', 'b'), ('c', 'b', 'a')]
```

<br>

### Task


You are given a string `S`.

Your task is to print all possible permutations of size `k` of the string in lexicographic sorted order.

<br>

### Input Format

A single line containing the space separated string `S` and the integer value `k`.


<br>

### Constraints


0 < `k` < `len(S)`

The string contains only UPPERCASE characters.


<br>

### Output Format

Print the permutations of the string `S` on separate lines.

<br>

**Sample Input**

```
HACK 2
```

<br>

**Sample Output**

```
AC
AH
AK
CA
CH
CK
HA
HC
HK
KA
KC
KH
```


<br>

**Explanation**

All possible size `2` permutations of the string `"HACK"` are printed in lexicographic sorted order.

<br>


## Solution

```python
from itertools import permutations

def per(s, size):
    return "\n".join(sorted(["".join(i) for i in permutations(s,size)]))


user = input().split(" ")

s, size = user[0], int(user[1])

print(per(s,size))
```
