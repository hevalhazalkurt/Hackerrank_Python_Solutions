# 027 - Merge the Tools!


## Problem

Consider the following:
* A string, `s`, of length `n` where *s = c<sub>0</sub>c<sub>1</sub>...c<sub>n-1</sub>*
* An integer, `k`, where `k` is a factor of `n`

We can split `s` into `n/k` subsegments where each subsegment, *t<sub>i</sub>*, consists of a contiguous block of `k` characters in `s`. Then, use each *t<sub>i</sub>* to create string *u<sub>i</sub>* such that:
* The characters in *u<sub>i</sub>* are a subsequence of the characters in *t<sub>i</sub>*
* Any repeat occurrence of a character is removed from the string such that each character in *u<sub>i</sub>* occurs exactly once. In other words, if the character at some index `j` in *t<sub>i</sub>* occurs at a previous index < `j` in *t<sub>i</sub>*, then do not include the character in string *u<sub>i</sub>*

Given `s` and `k`, print `n/k` lines where each line `i` denotes string *u<sub>i</sub>*

<br>


### Input Format

The first line contains a single string denoting `s`.

The second line contains an integer, `k`, denoting the length of each subsegment.

<br>

### Constraints


* 1 <= `n` <= 10<sup>4</sup>, where `n` is the length of `s`
* 1 <= `k` <= `n`
* It is guaranteed that `n` is a multiple of `k`



<br>



### Output Format

Print `n/k` lines where each line `i` contains string *u<sub>i</sub>*

<br>



**Sample Input**



```
AABCAAADA
3
```

<br>


**Sample Output**


```
AB
CA
AD
```


<br>


**Explanation**

String `s` is split into `n/k = 9/3 = 3` equal parts of length `k = 3`. We convert each *t<sub>i</sub>* to *u<sub>i</sub>* by removing any subsequent occurrences non-distinct characters in *t<sub>i</sub>*:

1. *t<sub>0</sub>* = `AAB` -> *u<sub>0</sub>* -> `AB`
2. *t<sub>1</sub>* = `CAA` -> *u<sub>1</sub>* -> `CA`
3. *t<sub>2</sub>* = `ADA` -> *u<sub>2</sub>* -> `AD`

We then print each *u<sub>i</sub>* on a new line.

<br>


### Given Code

```python
def merge_the_tools(string, k):
    # your code goes here

if __name__ == '__main__':
    string, k = raw_input(), int(raw_input())
    merge_the_tools(string, k)
```


<br>


## Solution 1

```python
def merge_the_tools(string, k):
    subs = [string[i:i+k] if i+k <= len(string) else string[i:] for i in range(0, len(string), k)]
    uniques = []
    for sub in subs:
        u = ""
        for char in sub:
            if char not in u:
                u = u + char
        uniques.append(u)
    print("\n".join(uniques))


if __name__ == '__main__':
    string, k = input(), int(input())
    merge_the_tools(string, k)
```


<br>


## Solution 2

```python
def merge_the_tools(string, k):
    uniques = []
    for i in range(0, len(string), k):
        u = ""
        for ch in string[i:i+k]:
            if ch not in u:
                u = u + ch
        uniques.append(u)
    print("\n".join(uniques))


if __name__ == '__main__':
    string, k = input(), int(input())
    merge_the_tools(string, k)
```
