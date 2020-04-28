# 047 - Word Order


## Problem


You are given `n` words. Some words may repeat. For each word, output its number of occurrences. The output order should correspond with the input order of appearance of the word. See the sample input/output for clarification.

**Note**: Each input line ends with a `"\n"` character.


<br>


### Constraints


1 <= `n` <= 10<sup>6</sup>

The sum of the lengths of all words do not exceed 10<sup>6</sup>.

All the words are composed of lowercase English letters only.



<br>

### Input Format

The first line contains the integer, `n`.

The next `n` lines each contain a word.



<br>



### Output Format

Output 2 lines.

On the first line, output the number of distinct words from the input.

On the second line, output the number of occurrences for each distinct word according to their appearance in the input.

<br>



**Sample Input**



```
4
bcdef
abcdefg
bcde
bcdef
```

<br>


**Sample Output**



```
3
2 1 1
```



<br>

**Explanation**

There are 3 distinct words. Here, `bcdef` appears twice in the input at the first and last positions. The other words appear once each. The order of the first appearances are `bcdef`,  `abcdefg` and `bcde` which corresponds to the output.


<br>


## Solution 1

```python
words = {}

for i in range(int(input())):
    word = input()
    if word in words:
        words[word] += 1
    else:
        words[word] = 1

print(len(words))
print(*[v for k,v in words.items()])
```


<br>


## Solution 2

```python
from collections import OrderedDict

words = OrderedDict()

for i in range(int(input())):
    word = input()
    if word in words:
        words[word] += 1
    else:
        words[word] = 1

print(len(words))
print(*[v for k,v in words.items()])
```
