# Day 1 : Data Types
## Problem
#### Objective
Today, we're discussing data types.

#### Task
Complete the code in the editor below. The variables `i`,`d` , and `s` are already declared and initialized for you. You must:

1. Declare 3 variables: one of type `int`, one of type `double`, and one of type `String`.

2. Read 3 lines of input from stdin (according to the sequence given in the `Input Format` section below) and initialize your 3 variables.

3. Use the + operator to perform the following operations:
 * Print the sum of `i` plus your int variable on a new line.
* Print the sum of `d` plus your double variable to a scale of one decimal place on a new line.
* Concatenate `s` with the string you read as input and print the result on a new line.

#### Input Format
The first line contains an integer that you must sum with `i`.

The second line contains a double that you must sum with `d`.

The third line contains a string that you must concatenate with `s`.

#### Output Format
Print the sum of both integers on the first line, the sum of both doubles (scaled to 1 decimal place) on the second line, and then the two concatenated strings on the third line.

```
Sample Input
12
4.0
is the best place to learn and practice coding!
```

```
16
8.0
HackerRank is the best place to learn and practice coding!
```

#### Explanation
When we sum the integers 4 and 12, we get the integer 16.

When we sum the floating-point numbers 4.0 and 4.0, we get 8.0.

When we concatenate `HackerRank` with `is the best place to learn and practice coding!`, we get `HackerRank is the best place to learn and practice coding!.`

<br>

---

<br>

## Given Code

```python
i = 4
d = 4.0
s = 'HackerRank '
# Declare second integer, double, and String variables.

# Read and save an integer, double, and String to your variables.

# Print the sum of both integer variables on a new line.

# Print the sum of the double variables on a new line.

# Concatenate and print the String variables on a new line
# The 's' variable above should be printed first.
```

## Solution

```python
i = 4
d = 4.0
s = 'HackerRank '

n = int(input())
f = float(input())
s = input()

print(i + n)
print(d + f)
print(s + s)
```


<br>

---

<br>


## Test Cases

**Input 1**

```
12
4.0
is the best place to learn and practice coding!
```

**Output 1**

```
16
8.0
is the best place to learn and practice coding!is the best place to learn and practice coding!
```

<br> <br>

**Input 2**

```
3
2.8
is my favorite platform!
```

**Output 2**

```
7
6.8
is my favorite platform!is my favorite platform!
```
