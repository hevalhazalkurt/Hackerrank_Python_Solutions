# 051 - Company Logo


## Problem

A newly opened multinational brand has decided to base their company logo on the three most common characters in the company name. They are now trying out various combinations of company names and logos based on this condition. Given a string `s`, which is the company name in lowercase letters, your task is to find the top three most common characters in the string.

* Print the three most common characters along with their occurrence count.
* Sort in descending order of occurrence count.
* If the occurrence count is the same, sort the characters in alphabetical order.

For example, according to the conditions described alone,

GOOGLE would have it's logo with the letters G, O, E.


<br>


### Input Format

A single line of input containing the string `S`.

<br>

### Constraints


3 < `len(S)` <= 10<sup>4</sup>



<br>



### Output Format

Print the three most common characters along with their occurrence count each on a separate line.

Sort output in descending order of occurrence count.

If the occurrence count is the same, sort the characters in alphabetical order.

<br>



**Sample Input**



```
aabbbccde
```

<br>


**Sample Output**


```
b 3
a 2
c 2
```


<br>


**Explanation**

`aabbbccde`

Here, b occurs 3 times. It is printed first.

Both a and c occur 2 times. So, a is printed in the second line and c in the third line because a comes before c in the alphabet.

Note: The string `S` has at least 3 distinct characters.

<br>


### Given Code

```python
import math
import os
import random
import re
import sys



if __name__ == '__main__':
    s = input()
```


<br>


## Solution

```python
import math
import os
import random
import re
import sys



if __name__ == '__main__':
    s = input()

    letters = {l:s.count(l) for l in s}
    print("\n".join([f"{l} {letters[l]}" for l in sorted(sorted(letters), key=lambda x: letters[x], reverse=True)[:3]]))
```
