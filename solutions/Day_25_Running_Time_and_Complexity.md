# Day 25 : Running Time and Complexity
## Problem
#### Objective


Today, we're learning about running time!

<br>

#### Task

A prime is a natural number greater than `1` that has no positive divisors other than `1` and itself. Given a number, `n`, determine and print whether it's `Prime` or `Not prime`.

**Note** : If possible, try to come up with a `O(√n)` primality algorithm, or see what sort of optimizations you come up with for an `O(n)` algorithm. Be sure to check out the Editorial after submitting your code.

<br>

#### Input Format

The first line contains an integer, `T`, the number of test cases.

Each of the `T` subsequent lines contains an integer, `n`, to be tested for primality.

<br>

#### Constraints

* 1 ≤ `T` ≤ 30
* 1 ≤ `n` ≤ 2 x 10<sup>9</sup>

<br>

#### Output Format

For each test case, print whether `n` is `Prime` or `Not prime` on a new line.

<br>

#### Sample Input


```
3
12
5
7
```

<br>

#### Sample Output


```
Not prime
Prime
Prime
```

<br>

#### Explanation

Test Case 0 : `n = 12`

`12` is divisible by numbers other than `1` and itself (i.e.: 2,3,6), so we print `Not prime` on a new line.

<br>

Test Case 1 : `n = 5`

`5` is only divisible `1` and itself, so we print `Prime` on a new line.

<br>

Test Case 2 : `n = 7`

`7` is only divisible `1` and itself, we print `Prime` on a new line.

<br>

## Given code

```python
# Enter your code here. Read input from STDIN. Print output to STDOUT
```


<br>

## Solution


```python
def isprime(n):
    if n == 1:
        return "Not prime"
    else:
        square_root = int(n**0.5)
        for i in range(2, square_root + 1):
            if ((n % i) == 0) and (i != n):
                return "Not prime"
        return "Prime"

for i in range(int(input(""))):
    print(isprime(int(input(""))))
```
