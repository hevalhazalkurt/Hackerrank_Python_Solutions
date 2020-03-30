# 015 - String Split and Join
## Problem

In Python, a string can be split on a delimiter.

**Example**

```python
>>> a = "this is a string"
>>> a = a.split(" ") # a is converted to a list of strings.
>>> print a
['this', 'is', 'a', 'string']
```

Joining a string is simple :

```python
>>> a = "-".join(a)
>>> print a
this-is-a-string
```


### Task

You are given a string. Split the string on a " " (space) delimiter and join using a - hyphen.

### Input Format

The first line contains a string consisting of space separated words.

### Output Format

Print the formatted string as explained above.


**Sample Input**

```
this is a string
```

**Sample Output**

```
this-is-a-string
```


<br>


### Given Code

```python
def split_and_join(line):
    # write your code here

if __name__ == '__main__':
    line = input()
    result = split_and_join(line)
    print(result)
```


## Solution

```python
def split_and_join(line):
    return "-".join(line.split())

if __name__ == '__main__':
    line = input()
    result = split_and_join(line)
    print(result)
```
