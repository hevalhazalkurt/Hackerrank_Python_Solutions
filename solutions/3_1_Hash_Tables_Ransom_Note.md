# The HackerRank Interview Preparation Kit
## 3. Dictionaries and Hashmaps

### 3.1. Hash Tables: Ransom Note

#### Problem

Harold is a kidnapper who wrote a ransom note, but now he is worried it will be traced back to him through his handwriting. He found a magazine and wants to know if he can cut out whole words from it and use them to create an untraceable replica of his ransom note. The words in his note are case-sensitive and he must use only whole words available in the magazine. He cannot use substrings or concatenation to create the words he needs.

Given the words in the magazine and the words in the ransom note, print Yes if he can replicate his ransom note exactly using whole words from the magazine; otherwise, print `No`.

For example, the note is "Attack at dawn". The magazine contains only "attack at dawn". The magazine has all the right words, but there's a case mismatch. The answer is `No`.

<br>

**Function Description**

Complete the `checkMagazine` function in the editor below. It must print `Yes` if the note can be formed using the magazine, or `No`.

`checkMagazine` has the following parameters:

- `magazine`: an array of strings, each a word in the magazine
- `note`: an array of strings, each a word in the ransom note

<br>

#### Input Format

The first line contains two space-separated integers, `m` and `n`, the numbers of words in the `magazine` and the `note`..

The second line contains `m` space-separated strings, each `magazine[i]`.

The third line contains `n` space-separated strings, each `note[i]`.

<br>

#### Constraints

* 1 <= `m,n` <= 30000
* 1 <= `|magazine[i]|`, `|note[i]|` <= 5
* Each word consists of English alphabetic letters (i.e., `a` to `z` and `A` to `Z`).


<br>

#### Output Format

Print `Yes` if he can use the magazine to create an untraceable replica of his ransom note. Otherwise, print `No`.

<br>

**Sample Input 0**

```
6 4
give me one grand today night
give one grand today
```

<br>

**Sample Output 0**

```
Yes
```


<br>

**Sample Input 1**

```
6 5
two times three is not four
two times two is four
```

<br>

**Sample Output 1**

```
No
```

<br>

**Explanation 1**

'two' only occurs once in the magazine.



<br>

**Sample Input 2**

```
7 4
ive got a lovely bunch of coconuts
ive got some coconuts
```

<br>

**Sample Output 2**

```
No
```

<br>

**Explanation 2**

Harold's magazine is missing the word `some`.

<br>



### Given Code

```python
import math
import os
import random
import re
import sys

# Complete the checkMagazine function below.
def checkMagazine(magazine, note):


if __name__ == '__main__':
    mn = input().split()

    m = int(mn[0])

    n = int(mn[1])

    magazine = input().rstrip().split()

    note = input().rstrip().split()

    checkMagazine(magazine, note)
```


## Solution 1

```python
import math
import os
import random
import re
import sys

# Complete the checkMagazine function below.
def checkMagazine(magazine, note):
    m_words = {w: magazine.count(w) for w in magazine}

    for w in note:
        if w not in m_words or note.count(w) > m_words[w]:
            print("No")
            return
    else:
        print("Yes")


if __name__ == '__main__':
    mn = input().split()

    m = int(mn[0])

    n = int(mn[1])

    magazine = input().rstrip().split()

    note = input().rstrip().split()

    checkMagazine(magazine, note)
```

---

## Solution 2

```python
def checkMagazine(magazine, note):
    m_words = {}
    n_words = {}

    for w in magazine:
        if w in m_words:
            m_words[w] += 1
        else:
            m_words[w] = 1

    for w in note:
        if w in n_words:
            n_words[w] += 1
        else:
            n_words[w] = 1

    print(m_words)
    print(n_words)

    for w in n_words:
        if w not in m_words:
            print("No")
            return
        else:
            if n_words[w] > m_words[w]:
                print("No")
                return
    else:
        print("Yes")


if __name__ == '__main__':
    mn = input().split()

    m = int(mn[0])

    n = int(mn[1])

    magazine = input().rstrip().split()

    note = input().rstrip().split()

    checkMagazine(magazine, note)
```


---

## Solution 3

```python
from collections import Counter

def checkMagazine(magazine, note):
    m = Counter(magazine)
    n = Counter(note)

    for w in n:
        if w not in m:
            return print("No")
        else:
            if m[w] < n[w]:
                return print("No")
    return print("Yes")


if __name__ == '__main__':
    mn = input().split()

    m = int(mn[0])

    n = int(mn[1])

    magazine = input().rstrip().split()

    note = input().rstrip().split()

    checkMagazine(magazine, note)
```
