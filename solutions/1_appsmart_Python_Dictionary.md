# The HackerRank Challenges
## appSMART : Python One

### 1. Python Dictionary

#### Problem
Welcome to last day of Python One Online A/L ICT Revision. We think now you all have a good knowledge in python. Now you are ready to get all marks for python questions in A/L ICT paper. Today we are going to use dictionaries. Today you have to help Sasindu to sort some image files. Think and code in python to help him.

Sasindu need to sort a list of image names according to their image number.

![](https://2.bp.blogspot.com/-ARBdXF-chmc/V2GCQKAes3I/AAAAAAAAAyw/SbunWcXAEYIRhFpSyeauUwy1YptvA0nQgCLcB/s320/img%2Bnumber.png)


All image names have the same format ('IMG' + image number + image format) such as IMG1.jpg, IMG2.jpg, IMG3.png, IMG6.bmp, etc.
Help him to sort them in ascending order according.
අද ඔබ සසිනිදුට පිංතූර කිහිපයක් අණුක්‍රමණයට උදව් වන්න. ඔබට ලැබෙන සියලු පිංතූර නාමයන් ('IMG' +පිංතූර අංකය + පිංතූර වර්ගය ) ලෙස වේ. උදහරණ IMG1.jpg, IMG2.jpg, IMG3.png, IMG6.bmp ආදී වශයෙනි්. සසිනිදු පිංතූර අංකය වැඩි වන ආකාරයට අනුක්‍රමණය කළ යුතුය.



<br>

#### Input Format

One line consists names of images separated by spaces.

<br>

#### Constraints


Image number > 0

<br>

#### Output Format

Print a list that contains all image names, sorted in ascending order using image number.

<br>

**Sample Input**

```
IMG1.jpg IMG11.jpg IMG2.jpg IMG20.png IMG19.jpg
```

<br>

**Sample Output**

```
['IMG1.jpg', 'IMG2.jpg', 'IMG11.jpg', 'IMG19.jpg', 'IMG20.png']
```


**Explanation**

Go to below link to learn more about python dictionaries http://shilpasayura.com/dev/python/

<br>


### Given Code

```python

```


## Solution

```python
def slicer(string):
    s = string.find("IMG")
    f = string.find(".")
    return int(string[s+3:f])

user = input()
user_list = user.split()

user_list = sorted(user_list, key= lambda x: slicer(x))
print(user_list)
```
