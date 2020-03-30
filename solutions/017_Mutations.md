# 017 - Mutations
## Problem

We have seen that lists are mutable (they can be changed), and tuples are immutable (they cannot be changed).

Let's try to understand this with an example.

You are given an immutable string, and you want to make changes to it.

**Example**

```
>>> string = "abracadabra"
```

You can access an index by:

```
>>> print(string[5])
a
```

What if you would like to assign a value?

```
>>> string[5] = 'k'
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'str' object does not support item assignment
```

How would you approach this?

* One solution is to convert the string to a list and then change the value.

**Example**

```
>>> string = "abracadabra"
>>> l = list(string)
>>> l[5] = 'k'
>>> string = ''.join(l)
>>> print string
abrackdabra
```

* Another approach is to slice the string and join it back.


**Example**

```
>>> string = string[:5] + "k" + string[6:]
>>> print string
abrackdabra
```


### Task

Read a given string, change the character at a given index and then print the modified string.


### Input Format

The first line contains a string, `S`.

The next line contains an integer `i`, denoting the index location and a character `c` separated by a space.


### Output Format

Using any of the methods explained above, replace the character at index `i` with character `c`.  

<br>

**Sample Input**

```
abracadabra
5 k
```

<br>

**Sample Output**

```
abrackdabra
```

<br>


### Given Code

```python
def mutate_string(string, position, character):
    return

if __name__ == '__main__':
    s = input()
    i, c = input().split()
    s_new = mutate_string(s, int(i), c)
    print(s_new)
```


## Solution

```python
def mutate_string(string, position, character):
    return "".join([character if e == position else c for e,c in enumerate(string)])

if __name__ == '__main__':
    s = input()
    i, c = input().split()
    s_new = mutate_string(s, int(i), c)
    print(s_new)
```
