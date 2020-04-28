# 037 - Collections.namedtuple()


## Problem

[collections.namedtuple()](https://docs.python.org/2/library/collections.html#collections.namedtuple)


Basically, namedtuples are easy to create, lightweight object types.

They turn tuples into convenient containers for simple tasks.

With namedtuples, you don't have to use integer indices for accessing members of a tuple.



**Example**

*Code 01*

```python
from collections import namedtuple

Point = namedtuple("Point", "x,y")
pt1 = Point(1,2)
pt2 = Point(3,4)
dot_product = (pt1.x * pt2.x) + (pt1.y * pt2.y)
print(pt1)
print(pt2)
print(dot_product)
```


```
Point(x=1, y=2)
Point(x=3, y=4)
11
```


<br>

*Code 02*

```python
from collections import namedtuple

Car = namedtuple("Car", "Price Mileage Colour Class")
xyz = Car(Price = 100000, Mileage = 30, Colour = "Cyan", Class = "Y")
print(xyz)
print(xyz.Price)
print(xyz.Class)
```


```
Car(Price=100000, Mileage=30, Colour='Cyan', Class='Y')
100000
Y
```



<br>


### Task


Dr. John Wesley has a spreadsheet containing a list of student's IDs, marks, class and name.

Your task is to help Dr. Wesley calculate the average marks of the students.


```
Average = Sum of all marks / Total Students
```


<sub>Note :<br></sub>
<sub>1. Columns can be in any order. IDs, marks, class and name can be written in any order in the spreadsheet.<br></sub>
<sub>2. Column names are `ID`, `MARKS`, `CLASS` and `NAME`. (The spelling and case type of these names won't change.) </sub>

<br>

### Input Format

The first line contains an integer `N`, the total number of students.

The second line contains the names of the columns in any order.

The next `N` lines contains the `marks`, `IDs`, `name` and `class`, under their respective column names.


<br>

### Constraints


1 <= `N` <= 100



<br>



### Output Format

Print the average marks of the list corrected to 2 decimal places.

<br>



**Sample Input**

*Testcase 01*

```
5
ID         MARKS      NAME       CLASS     
1          97         Raymond    7         
2          50         Steven     4         
3          91         Adrian     9         
4          72         Stewart    5         
5          80         Peter      6
```

<br>

*Testcase 01*

```
5
MARKS      CLASS      NAME       ID        
92         2          Calum      1         
82         5          Scott      2         
94         2          Jason      3         
55         8          Glenn      4         
82         2          Fergus     5
```

<br>

**Sample Output**


*Testcase 01*

```
78.00
```


<br>

*Testcase 02*

```
81.00
```


<br>

**Explanation**

*Testcase 01*

Average = (97 + 50 + 91 + 72 + 80) / 5

Can you solve this challenge in 4 lines of code or less?

NOTE : There is no penalty for solutions that are correct but have more than 4 lines.


<br>


## Solution 

```python
from collections import namedtuple

N = int(input().strip())
Student = namedtuple("Student", ",".join(input().strip().split()))

print(format(sum([int(i.MARKS) for i in [Student(*input().strip().split()) for _ in range(N)]]) / N, '.2f'))
```
