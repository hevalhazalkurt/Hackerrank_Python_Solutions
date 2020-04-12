# 023 - Alphabet Rangoli

## Problem

You are given an integer, `N`, Your task is to print an alphabet rangoli of size `N`. (Rangoli is a form of Indian folk art based on creation of patterns.)

Different sizes of alphabet rangoli are shown below:

```
#size 3

----c----
--c-b-c--
c-b-a-b-c
--c-b-c--
----c----

#size 5

--------e--------
------e-d-e------
----e-d-c-d-e----
--e-d-c-b-c-d-e--
e-d-c-b-a-b-c-d-e
--e-d-c-b-c-d-e--
----e-d-c-d-e----
------e-d-e------
--------e--------

#size 10

------------------j------------------
----------------j-i-j----------------
--------------j-i-h-i-j--------------
------------j-i-h-g-h-i-j------------
----------j-i-h-g-f-g-h-i-j----------
--------j-i-h-g-f-e-f-g-h-i-j--------
------j-i-h-g-f-e-d-e-f-g-h-i-j------
----j-i-h-g-f-e-d-c-d-e-f-g-h-i-j----
--j-i-h-g-f-e-d-c-b-c-d-e-f-g-h-i-j--
j-i-h-g-f-e-d-c-b-a-b-c-d-e-f-g-h-i-j
--j-i-h-g-f-e-d-c-b-c-d-e-f-g-h-i-j--
----j-i-h-g-f-e-d-c-d-e-f-g-h-i-j----
------j-i-h-g-f-e-d-e-f-g-h-i-j------
--------j-i-h-g-f-e-f-g-h-i-j--------
----------j-i-h-g-f-g-h-i-j----------
------------j-i-h-g-h-i-j------------
--------------j-i-h-i-j--------------
----------------j-i-j----------------
------------------j------------------
```


The center of the rangoli has the first alphabet letter `a`, and the boundary has the N<sup>th</sup> alphabet letter (in alphabetical order).

<br>

### Input Format

Only one line of input containing `N`, the size of the rangoli.


### Constraints


0 < `N` < 27



### Output Format

Print the alphabet rangoli in the format explained above.

<br>

**Sample Input**

```
5
```

<br>

**Sample Output**

```
--------e--------
------e-d-e------
----e-d-c-d-e----
--e-d-c-b-c-d-e--
e-d-c-b-a-b-c-d-e
--e-d-c-b-c-d-e--
----e-d-c-d-e----
------e-d-e------
--------e--------
```



<br>


### Given Code

```python
def print_rangoli(size):
    # your code goes here

if __name__ == '__main__':
    n = int(input())
    print_rangoli(n)
```


## Solution

```python
def print_rangoli(size):
    alphabet = "abcdefghijklmnopqrstuvwxyz"[:size]
    center = "-".join([c for c in alphabet[::-1]] + [c for c in alphabet[1:]])
    design = []
    for i in range(1, size+1):
        letters = [c for c in alphabet[-i:]]
        if len(letters) == 1:
            design.append("-".join(letters).center(len(center), "-"))
        else:
            design.append("-".join(letters[::-1] + letters[1:]).center(len(center), "-"))

    print("\n".join(design + design[::-1][1:]))

if __name__ == '__main__':
    n = int(input())
    print_rangoli(n)
```
