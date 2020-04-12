# 025 - The Minion Game

## Problem

Kevin and Stuart want to play the **The Minion Game**.

**Game Rules**

Both players are given the same string `S`. <br>
Both players have to make substrings using the letters of the string `S`. <br>
Stuart has to make words starting with consonants. <br>
Kevin has to make words starting with wovels. <br>
The game ends when both players have made all possible substrings.

<br>

**Scoring**

A player gets +1 point for each occurrence of the substring in the string `S`.

<br>

**For Example**

String `S = BANANA` <br>
Kevin's wovel beginning word = `ANA` <br>
Here, `ANA` occurs twice in `BANANA`. Hence, Kevin will get 2 points.


<br>

For better understanding, see the image below :

![](https://s3.amazonaws.com/hr-challenge-images/9693/1450330231-04db904008-banana.png)


<br>

### Input Format

A single line of input containing the full name, `S`. <br>

**Note** : The string `S` will contain only uppercase letters: `[A - Z]`.


<br>

### Constraints


0 < `len(S)` < 10<sup>6</sup>


<br>

### Output Format

Print one line : the name of the winner and their score separated by a space.

If the game is a draw, print `Draw`

<br>

**Sample Input**

```
BANANA
```

<br>

**Sample Output**

```
Stuart 12
```



<br>


<sub>**Note**: Vowels are only defined as `AEIOU`. In this problem, `Y` is not considered a vowel.</sub>

<br>


### Given Code

```python
def minion_game(string):
    # your code goes here

if __name__ == '__main__':
    s = input()
    minion_game(s)
```


## Solution

```python
def minion_game(string):
    wovels = "AEIOU"

    kev = 0
    stu = 0

    for i in range(len(string)):
        if s[i] in wovels:
            kev += len(string)-i
        else:
            stu += len(string)-i

    if kev > stu:
        print("Kevin", kev)
    elif kev < stu:
        print("Stuart", stu)
    else:
        print("Draw")
```
