# Day 14: Scope
## Problem
#### Objective

Today, we're discussing scope.

The absolute difference between two integers, `a` and `b`, is written as `|a-b|`. The maximum absolute difference between two integers in a set of positive integers, `elements`, is the largest absolute difference between any two integers in `eşements`.

#### Task
Complete the `Difference` class by writing the following :

- A class constructor that takes an array of integers as a parameter and saves it to the `elements` instance variable.
- A `computeDifference` method that finds the maximum absolute difference between any 2 numbers in `N` and stores it in the `maximumDifference` instance variable.


#### Input Format
You are not responsible for reading any input from stdin. The locked `Solution` class in your ediyor reads in 2 lines of input; the first line contains `N`, and the secon line describes the `elements` array.


#### Constraints

* a <= `N` <= 10
* a <= `elements[i]` <= 100, where 0 <= `i` <= `N`-1


#### Output Format
You are not responsible for printing any output; the `Solution` class will print the value of the `maximumDifference` instance variable.



#### Sample Input


```
3
1 2 5
```

#### Sample Output


```
4
```


#### Explanation

The scope of the `elements` array and `maximumDifference` integer is the entire class instance. The class constructor saves the argument passed to the constructor as the `elements` instance variable (where the `computeDifference` method can access it.)

To find the maximu difference, `computeDifference` chechs each element in the array and finds the maximum difference between any 2 elements:

|1-2| = 1 <br>
|1-5| = 4 <br>
|2-5| = 3 <br>

The maximum of these differences is 4, so it saves the value `4` as the `maximumDifference` instance variable. The locked stub code in the editor then prints the value stored as `maximumDifference`, whics is 4.


## Given code

```python
class Difference:
    def __init__(self, a):
        self.__elements = a

	# Add your code here

# End of Difference class

_ = input()
a = [int(e) for e in input().split(' ')]

d = Difference(a)
d.computeDifference()

print(d.maximumDifference)
```

## Solution

```python
class Difference:
    def __init__(self, a):
        self.__elements = a
        self.maximumDifference = None

    def computeDifference(self):
        a_len = len(a)
        for i in a:
            for n in range(a_len):
                num = abs(i - a[n])
                if self.maximumDifference == None:
                    self.maximumDifference = num
                elif num > self.maximumDifference:
                    self.maximumDifference = num
        return self.maximumDifference

_ = input()
a = [int(e) for e in input().split(' ')]
print(a)

d = Difference(a)
d.computeDifference()

print(d.maximumDifference)
```
