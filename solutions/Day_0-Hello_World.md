# HackerRank - 30 Days of Python
## Day 0 : Hello, World
### Problem
#### Objective
In this challenge, we review some basic concepts that will get you started with this series. You will need to use the same (or similar) syntax to read input and write output in challenges throughout HackerRank.

#### Task
To complete this challenge, you must save a line of input from stdin to a variable, print Hello, World. on a single line, and finally print the value of your variable on a second line.


#### Output Format
Print `Hello, World.` on the first line, and the contents of `inputString` on the second line.


#### Given Code

```python
# Read a full line of input from stdin and save it to our dynamically typed variable, input_string.
input_string = input()

# Print a string literal saying "Hello, World." to stdout.
print('Hello, World.')

# TODO: Write a line of code here that prints the contents of input_string to stdout.
```

## Solution
Below you'll find two separate solutions, one with two small differences. Because [HackerRank](https://www.hackerrank.com/)'s `input` part on first line in given code does not run when running in your own text editor and terminal. When I rearranged the code in my local text editor and terminal, HackerRank gives an error. That's why you can find the code versions that work in both the HackerRank system and on the local below.

```python
input_string = input()
print('Hello, World.')
print(input_string)
```

**Output**

```
Hello, World.
Welcome to 30 Days of Code!
```
