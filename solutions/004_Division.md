# 004 - Division
## Task
Read two integers and print two lines. The first line should contain integer division,  `a` // `b` . The second line should contain float division,  `a`/`b` .

You don't need to perform any rounding or formatting operations.

#### Input Format

The first line contains the first integer, `a`. The second line contains the second integer, `b`.


#### Output Format

Print the two lines as described above.

```
Sample Input :
4
3
```

```
Sample Output :
1
1.33333333333
```

#### Given Code

```python
if __name__ == '__main__':
    a = int(input())
    b = int(input())
```

## Solution 1

```python
if __name__ == '__main__':
    a = int(input())
    b = int(input())

    print(int(a / b))
    print(float(a / b))
```

## Solution 2

```python
if __name__ == '__main__':
    a = int(input())
    b = int(input())

    def division_int(x,y):
        return x // y

    def division_flt(x,y):
        return x / y

    print(division_int(a,b))
    print(division_flt(a,b))
```
