# Day 6 : Let's Review
## Problem
#### Objective
Today we're expanding our knowledge of Strings and combining it with what we've already learned about loops.

#### Task
Given a string, `S`, of length `N` that is indexed from 0 to `N - 1`, print its even-indexed and odd-indexed characters as 2 space-separated strings on a single line (see the Sample below for more detail).

**Note:** 0 is considered to be an even index.

#### Input Format
The first line contains an integer, `T` (the number of test cases).
Each line `i` of the `T` subsequent lines contain a String,`S`.

#### Constraints
1 <= T <= 10

2 <= lenght of S <= 10000

#### Output Format
For each String S<sub>j</sub> (where 0 <= j <= T - 1), print S<sub>j</sub>'s even-indexed characters, followed by a space, followed by S<sub>j</sub>'s odd-indexed characters.

```
Sample Input
2
Hacker
Rank
```

```
Sample Output
Hce akr
Rn ak
```

#### Explanation
Test Case 0:  S = "Hacker"
S[0] = "H"
S[1] = "a"
S[2] = "c"
S[3] = "k"
S[4] = "e"
S[5] = "r"

The even indices are 0, 2, and 4, and the odd indices are 1, 3, and 5. We then print a single line of 2 space-separated strings; the first string contains the ordered characters from S's even indices (Hce), and the second string contains the ordered characters from 's odd indices (akr).

Test Case 1:  S = "Rank"
S[0] = "R"
S[1] = "a"
S[2] = "n"
S[3] = "k"

The even indices are 0 and 2, and the odd indices are 1 and 3. We then print a single line of 2 space-separated strings; the first string contains the ordered characters from S's even indices (Rn), and the second string contains the ordered characters from S's odd indices (ak).


---

## Given Code

```python
# Enter your code here. Read input from STDIN. Print output to STDOUT
```

## Solution 1

```python
T = input()
for N in range(int(T)):
    S = input()
    print(S[::2], S[1::2])
```

## Solution 2

```python
inputs = int(input())

for n in range(inputs):
    user = input()
    evens = ""
    odds = ""

    i = 0

    for char in user:
        if i % 2 == 0:
            evens += char
        else:
            odds += char
        i += 1

    print("{} {}".format(evens,odds))
```


## Solution 3

```python
N = int(input())

for i in range(0, N):
    string = input()
    for j in range(0, len(string)):
        if j % 2 == 0:
            print(string[j], end='')
    print(" ", end='')

    for j in range(0, len(string)):
        if j % 2 != 0:
            print(string[j], end='')
    print("")
```
