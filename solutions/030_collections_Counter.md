# 030 - collections.Counter()

## Problem

[collections.Counter()](https://docs.python.org/2/library/collections.html#collections.Counter)

A counter is a container that stores elements as dictionary keys, and their counts are stored as dictionary values.


**Sample Code**

```python
from collections import Counter

myList = [1,1,2,3,4,5,3,2,3,4,2,1,2,3]

print(Counter(myList))
print(Counter(myList).items())
print(Counter(myList).keys())
print(Counter(myList).values())
```

```
Counter({2: 4, 3: 4, 1: 3, 4: 2, 5: 1})
dict_items([(1, 3), (2, 4), (3, 4), (4, 2), (5, 1)])
dict_keys([1, 2, 3, 4, 5])
dict_values([3, 4, 4, 2, 1])
```

<br>

### Task


`Raghu` is a shoe shop owner. His shop has `X` number of shoes.

He has a list containing the size of each shoe he has in his shop.

There are `N` number of customers who are willing to pay **x<sub>i</sub>** amount of money only if they get the shoe of their desired size.

Your task is to compute how much money `Raghu` earned.

<br>

### Input Format

The first line contains `X`, the number of shoes.

The second line contains the space separated list of all the shoe sizes in the shop.

The third line contains `N`, the number of customers.

The next `N` lines contain the space separated values of the `shoe size` desired by the customer and **x<sub>i</sub>**, the price of the shoe.


<br>

### Constraints


* 0 < `X` < 10<sup>3</sup>
* 0 < `N` < 10<sup>3</sup>
* 20 < **x<sub>i</sub>** < 100
* 2 < `shoe size` < 20


<br>

### Output Format

Print the amount of money earned by `Raghu`.

<br>

**Sample Input**

```
10
2 3 4 5 6 8 7 6 5 18
6
6 55
6 45
6 55
4 40
18 60
10 50
```

<br>

**Sample Output**

```
200
```


<br>

**Explanation**

Customer 1 : Purchased size 6 shoe for $55 <br>
Customer 2 : Purchased size 6 shoe for $45 <br>
Customer 3 : Size 6 no longer available, so no purchase <br>
Customer 4 : Purchased size 4 shoes for $40 <br>
Customer 5 : Purchased size 18 show for $60 <br>
Customer 6 : Size 10 not available, so no purchase <br>

Total money earned = 55 + 45 + 40 + 60 = $200

<br>


## Solution

```python
from collections import Counter


def earned(sales, stock):
    earned = 0

    for i in range(sales):
        sale = input().split(" ")
        shoe, price = sale[0], int(sale[1])

        if shoe in stock and stock[shoe] >= 1:
            earned += price
            stock[shoe] -= 1
        else:
            continue

    return earned


stock_len = int(input())
stock = dict(Counter([i for i in input().split(" ")]))
sales = int(input())



print(earned(sales, stock))
```
