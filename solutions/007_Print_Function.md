# 007 - Print Function
## Task
Read an integer `N` .

Without using any string methods, try to print the following:
`123...N`

Note that "..." represents the values in between.

#### Input Format

The first line contains an integer `N`.


#### Output Format

Output the answer as explained in the task.

```
Sample Input :
3
```

```
Sample Output :
123
```


#### Given Code

```python
if __name__ == '__main__':
    n = int(input())
```

----

## Solution 1

```python
if __name__ == '__main__':
    n = int(input())
    print(*range(1, n + 1), sep="")
```


## Solution 2

```python
if __name__ == '__main__':
    n = int(input())
    print("".join([str(x) for x in range(1,n+1)]))
```


## Solution 3

```python
if __name__ == '__main__':
    n = int(input())
    lst = [x for x in range(1,n+1)]
    print(*lst, sep="")
```


## Solution 4

```python
if __name__ == '__main__':
    n = int(input())
    lst = ""
    for num in range(1, n+1):
      lst += str(num)
    print(lst)
```

## Solution 5

```python
if __name__ == '__main__':
    n = int(input())
    lst = []
    for num in range(1, n+1):
      lst.append(str(num))
    print("".join(lst))
```
