# 010 - Nested Lists
## Problem
Given the names and grades for each student in a Physics class of `N` students, store them in a nested list and print the name(s) of any student(s) having the second lowest grade.

**Note**: If there are multiple students with the same grade, order their names alphabetically and print each name on a new line.

#### Input Format

The first line contains an integer, `N`, the number of students.

The `2N` subsequent lines describe each student over `N` lines; the first line contains a student's name, and the second line contains their grade.


#### Constraints
2 <= N <= 5

There will always be one or more students having the second lowest grade.

#### Output Format

Print the name(s) of any student(s) having the second lowest grade in Physics; if there are multiple students, order their names alphabetically and print each one on a new line.

```
Sample Input :
5
Harry
37.21
Berry
37.21
Tina
37.2
Akriti
41
Harsh
39
```

```
Sample Output :
Berry
Harry
```

#### Explanation
There are 5 students in this class whose names and grades are assembled to build the following list:

`python students = [['Harry', 37.21], ['Berry', 37.21], ['Tina', 37.2], ['Akriti', 41], ['Harsh', 39]]`

The lowest grade of 37.2 belongs to Tina. The second lowest grade of 37.21 belongs to both Harry and Berry, so we order their names alphabetically and print each name on a new line.


#### Given Code

```python
if __name__ == '__main__':
    for _ in range(int(input())):
        name = input()
        score = float(input())
```


## Solution

```python
if __name__ == '__main__':
    students = []
    for _ in range(int(input())):
        name = input()
        score = float(input())
        students.append([name, score])
    mn = min(students, key=lambda x: x[1])
    nonlowest = sorted([student for student in students if student[1] > mn[1]], key= lambda x: x[1])
    seconds = sorted([student[0] for student in nonlowest if student[1] == nonlowest[0][1]])
    for student in seconds:
        print(student)
```
