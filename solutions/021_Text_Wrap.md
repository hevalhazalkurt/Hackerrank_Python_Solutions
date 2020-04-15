# 021 - Text Wrap

## Task

You are given a string `S` and width `w`.

Your task is to wrap the string into a paragraph of width `w`.

<br>

### Input Format

The first line contains a string, `S`.

The second line contains the width, `w`.


### Constraints


0 < `len(S)` < 1000 <br>
0 < `w` < `len(S)`



### Output Format

Print the text wrapped paragraph.

<br>

**Sample Input**

```
ABCDEFGHIJKLIMNOQRSTUVWXYZ
4
```

<br>

**Sample Output**

```
ABCD
EFGH
IJKL
IMNO
QRST
UVWX
YZ
```



<br>


### Given Code

```python
import textwrap

def wrap(string, max_width):
    return

if __name__ == '__main__':
    string, max_width = input(), int(input())
    result = wrap(string, max_width)
    print(result)
```


## Solution

```python
import textwrap

def wrap(string, max_width):
    return "\n".join([string[i:i+max_width] for i in range(0, len(string), max_width)])

if __name__ == '__main__':
    string, max_width = input(), int(input())
    result = wrap(string, max_width)
    print(result)
```
