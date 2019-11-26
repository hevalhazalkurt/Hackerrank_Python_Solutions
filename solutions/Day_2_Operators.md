# Day 2 : Operators
## Problem
#### Objective
In this challenge, you'll work with arithmetic operators.

#### Task
Given the meal price (base cost of a meal), tip percent (the percentage of the meal price being added as tip), and tax percent (the percentage of the meal price being added as tax) for a meal, find and print the meal's total cost.

***Note:*** Be sure to use precise values for your calculations, or you may end up with an incorrectly rounded result!

#### Input Format
There are 3 lines of numeric input:
The first line has a double,  `mealCost` (the cost of the meal before tax and tip).
The second line has an integer, `tipPercent` (the percentage of  being added as tip).
The third line has an integer, `taxPercent` (the percentage of  being added as tax).

#### Output Format
Print the total meal cost, where `totalCost` is the rounded integer result of the entire bill ( `mealCost` with added tax and tip).

```
Sample Input
12.00
20
8
```

```
Sample Output
15
```

#### Explanation
**Given:**

`mealCost` = 12

`tipPercent` = 20

`taxPercent` = 8

**Calculations:**

tip = 12 x 20 / 100 = 2.4
tax = 12 x 8 / 100 = 0.96
totalCost = mealCost + tip + tax = 12 + 2.4 + 0.96 = 15.36
round(totalCost) = 15  

We round `totalCost` to the nearest dollar (integer) and then print our result, 15 .

#### Given Code

```python
import math
import os
import random
import re
import sys

# Complete the solve function below.
def solve(meal_cost, tip_percent, tax_percent):

if __name__ == '__main__':
    meal_cost = float(input())

    tip_percent = int(input())

    tax_percent = int(input())

    solve(meal_cost, tip_percent, tax_percent)
```

## Solution 1

```python
import math
import os
import random
import re
import sys

# Complete the solve function below.
def solve(meal_cost, tip_percent, tax_percent):
    tip = float(meal_cost * (tip_percent / 100))
    tax = float(meal_cost * (tax_percent / 100))
    totalCost = float(meal_cost) + tip + tax
    print(round(totalCost))

if __name__ == '__main__':
    meal_cost = float(input())

    tip_percent = int(input())

    tax_percent = int(input())

    solve(meal_cost, tip_percent, tax_percent)
```

---


## Solution 2

```python
import math
import os
import random
import re
import sys

# Complete the solve function below.
def solve(meal_cost, tip_percent, tax_percent):
    tip = meal_cost * tip_percent / 100
    tax = meal_cost * tax_percent /100
    totalCost = meal_cost + tip + tax
    print(round(totalCost))

if __name__ == '__main__':
    meal_cost = float(input())

    tip_percent = int(input())

    tax_percent = int(input())

    solve(meal_cost, tip_percent, tax_percent)
```


---

## Solution 3

```python
import math
import os
import random
import re
import sys

# Complete the solve function below.
def solve(meal_cost, tip_percent, tax_percent):
  totalCost = meal_cost + (meal_cost * tip_percent / 100) + (meal_cost * tax_percent / 100)
  print(round(totalCost))

if __name__ == '__main__':
    meal_cost = float(input())

    tip_percent = int(input())

    tax_percent = int(input())

    solve(meal_cost, tip_percent, tax_percent)
```


---

## Test Cases

**Input 1**

```
12
20
8
```

**Output 1**

```
15
```

<br> <br>

**Input 2**

```
15.50
15
10
```

**Output 2**

```
19
```
