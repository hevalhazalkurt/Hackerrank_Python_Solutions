# 005 - Loops
## Task
Read an integer `N`. For all non-negative integers `i < N`, print **i<sup>2</sup>**. See the sample for details.

#### Input Format

The first and only line contains the integer, `N`.

#### Constraints
1 <= N <= 20

#### Output Format

Print `N` lines, one corresponding to each `i`.

```
Sample Input :
5
```

```
Sample Output :
0
1
4
9
16
```

#### Given Code

```python
if __name__ == '__main__':
    n = int(input())
```


## Solution 1

```python
if __name__ == '__main__':
    n = int(input())

    for i in range(n):
        print(i**2)
```


## Solution 2

```python
if __name__ == '__main__':
    n = int(input())
    i = 0
    while i < n:
        r = i * i
        i = i + 1
        print(r)
```
