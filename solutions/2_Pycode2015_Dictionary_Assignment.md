# The HackerRank Challenges
## Pycode2015

### Dictionary-Assignment

#### Problem

Write a function `histogram()` that takes a string and builds a frequency listing of the characters contained in it. Represent the frequency listing as a Python dictionary and print the in sorted order on 'key'.



<br>

#### Input Format

For each `"T"` test cases, we have one line:

First line contains a strings for which the frequecy of characters to be generated

1 <= `T` <= 500

1 <= `N` <= 100

<br>



#### Output Format

For each of the test cases, print a dictionary that maps from frequencies to letters. For Eg.

`for string S="'brontosaurus'`

the program should create a dictionary

`hist={'a': 1, 'b': 1, 'o': 2, 'n': 1, 's': 2, 'r': 2, 'u': 2, 't': 1}`

The dictionary `'hist'` indicates that the letters `’a’` and `'b'` appear once; `'o'` appears twice, and so on.

sort a dict by keys and print


```
Letter a apperas 1 time/s
Letter b appears 1 time/s
Letter n appears 1 time/s
Letter o apperas 2 time/s
........
Letter u appears 2 time/s
```

<br>

**Sample Input**

```
2
abracadabra
msrit
```

<br>

**Sample Output**

```
Letter a  appears  5  time/s
Letter b  appears  2  time/s
Letter c  appears  1  time/s
Letter d  appears  1  time/s
Letter r  appears  2  time/s

Letter i  appears  1  time/s
Letter m  appears  1  time/s
Letter r  appears  1  time/s
Letter s  appears  1  time/s
Letter t  appears  1  time/s
```


**Explanation**

The function dict creates a new dictionary with no items. Because dict is the name of a built-in function, you should avoid using it as a variable name.

```python
>>> eng2sp = dict()
>>> print eng2sp
{}
```

The squiggly-brackets, {}, represent an empty dictionary. To add items to the dictionary, you can use square brackets:


```python
>>> eng2sp['one'] = 'uno'
```

**Important Note:**

If we want to order or sort the dictionary objects by their keys, the simplest way to do so is by Python's built-in "sorted" method, which will take any iterable and return a list of the values which has been sorted (in ascending order by default)

<br>



## Solution 1

```python
def histogram(string):
    hist = {c:string.count(c) for c in string}
    return "\n".join(sorted([f"Letter {k}  appears  {v}  time/s" for k,v in hist.items()]))

word = input("")

print(histogram(word))
```

<br>



## Solution 2

```python
def histogram(string):
    hist = {}

    for c in string:
        if c in hist:
            hist[c] += 1
        else:
            hist[c] = 1

    for k,v in sorted(hist.items()):
        print(f"Letter {k}  appears  {v}  time/s")


histogram(input(""))
```
