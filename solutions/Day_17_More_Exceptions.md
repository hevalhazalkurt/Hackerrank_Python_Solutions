# Day 17 : More Exceptions
## Problem
#### Objective

Yesterday's challenge taught you to manage exceptional situations by using try and catch blocks. In today's challenge, you're going to practice throwing and propagating an exception.


#### Task

Write a `Calculator` class with a single method: `int power(int,int)`. The power method takes two integers `n` and `p`, as parameters and returns the integer result of ***n<sup>p</sup>***. If either `n` or `p` is negative, then the method must throw an exception with the message : `n and p should be non-negative`.

Note : Do not use an access modifier (e.g.: public) in the declaration for your `Calculator` class.

#### Input Format

Input from stdin is handled for you by the locked stub code in your code editor. The first line contains an integer, `T`, the number of test cases. Each of `T` subsequent lines describes a test case in 2 space-separated integers denoting `n` and `p`, respectively.


#### Constraints

No Test Case will result in overflow for correctly written code.


#### Output Format

Output to stdout is handled for you by the locked stub code in your editor. There are `T` lines of output, where each line contains the result of ***n<sup>p</sup>*** as calculated by your `Calculator` class' power method.

#### Sample Input


```
4
3 5
2 4
-1 -2
-1 3
```

#### Sample Output


```
243
16
n and p should be non-negative
n and p should be non-negative
```


#### Explanation

`T = 4`

***T<sub>0</sub>*** : `3` and `5` are positive so power returns the result of  ***3<sup>3</sup>*** which is `243`

***T<sub>1</sub>*** : `2` and `4` are positive so power returns the result of  ***2<sup>4</sup>*** which is `16`

***T<sub>2</sub>*** : Both inputs, `-1` and `-2` are negative, so power throws an exception `n and p should be non-negative` is printed.

***T<sub>3</sub>*** : One of the inputs `-1` is negative, so power throws an exception `n and p should be non-negative` is printed.


## Given code

```python
#Write your code here

myCalculator=Calculator()
T=int(input())
for i in range(T):
    n,p = map(int, input().split())
    try:
        ans=myCalculator.power(n,p)
        print(ans)
    except Exception as e:
        print(e)   
```



## Solution


```python
class Calculator:

    def power(self, n, p):
        if n < 0 or p < 0:
            raise Exception("n and p should be non-negative")
        else:
            return n**p

myCalculator=Calculator()
T=int(input())
for i in range(T):
    n,p = map(int, input().split())
    try:
        ans=myCalculator.power(n,p)
        print(ans)
    except Exception as e:
        print(e)
```
