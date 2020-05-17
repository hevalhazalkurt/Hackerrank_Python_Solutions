# Day 27 : Testing
## Problem

This problem is all about unit testing.

Your company needs a function that meets the following requirements:
* For a given array of `n` integers, the function returns the index of the element with the minimum value in the array. If there is more than one element with the minimum value, th returned index should be the smallest one.
* If an empty array is passed to the function, it should raise an Exception.

Note: The arrays are indexed from `0`.

A colleague has written that function, and your task is to design `3` separated unit tests, testing if the function behaves correctly. The implementation in Python is listed below (implementations in other languages can be found in the code template):

```python
def minimum_index(seq):
    if len(seq) == 0:
        raise ValueError("Cannot get the minimum value index from an empty sequence")
    min_idx = 0
    for i in range(1, len(seq)):
        if a[i] < a[min_idx]:
            min_idx = i
    return min_idx
```

Another co-worker has prepared functions that will perform the testing and validate returned results with expectations. Your task is to implement `3` classes that will produce test data and the expected results for the testing functions. More specifically:

function `get_array()` in `TestDataEmptyArray` class and functions `get_array()` and `get_expected_result()` in classes `TestDataUniqueValues` and `TestDataExactlyTwoDifferentMinimums` following the below specifications:
* `get_array()` method in class `TestDataEmptyArray` has to return an empty array
* `get_array()` method in class `TestDataUniqueValues` has to return an array of size at least 2 with all unique elements, while method `get_expected_result()` of this class has to return the expected minimum value index for this array
* `get_array()` method in class `TestDataExactlyTwoDifferentMinimums` has to return an array where there are exactly two different minimum values, while method `get_expected_result()` of this class has to return the expected minimum value index for this array

Take a look at the code template to see the exact implementation of function that your colleagues already implemented.

<br>

## Given code

```python
def minimum_index(seq):
    if len(seq) == 0:
        raise ValueError("Cannot get the minimum value index from an empty sequence")
    min_idx = 0
    for i in range(1, len(seq)):
        if seq[i] < seq[min_idx]:
            min_idx = i
    return min_idx
class TestDataEmptyArray(object):

    @staticmethod
    def get_array():
        # complete this function

class TestDataUniqueValues(object):

    @staticmethod
    def get_array():
        # complete this function

    @staticmethod
    def get_expected_result():
        # complete this function

class TestDataExactlyTwoDifferentMinimums(object):

    @staticmethod
    def get_array():
        # complete this function

    @staticmethod
    def get_expected_result():
        # complete this function


def TestWithEmptyArray():
    try:
        seq = TestDataEmptyArray.get_array()
        result = minimum_index(seq)
    except ValueError as e:
        pass
    else:
        assert False


def TestWithUniqueValues():
    seq = TestDataUniqueValues.get_array()
    assert len(seq) >= 2

    assert len(list(set(seq))) == len(seq)

    expected_result = TestDataUniqueValues.get_expected_result()
    result = minimum_index(seq)
    assert result == expected_result


def TestiWithExactyTwoDifferentMinimums():
    seq = TestDataExactlyTwoDifferentMinimums.get_array()
    assert len(seq) >= 2
    tmp = sorted(seq)
    assert tmp[0] == tmp[1] and (len(tmp) == 2 or tmp[1] < tmp[2])

    expected_result = TestDataExactlyTwoDifferentMinimums.get_expected_result()
    result = minimum_index(seq)
    assert result == expected_result

TestWithEmptyArray()
TestWithUniqueValues()
TestiWithExactyTwoDifferentMinimums()
print("OK")
```


<br>

## Solution


```python
def minimum_index(seq):
    if len(seq) == 0:
        raise ValueError("Cannot get the minimum value index from an empty sequence")
    min_idx = 0
    for i in range(1, len(seq)):
        if seq[i] < seq[min_idx]:
            min_idx = i
    return min_idx
class TestDataEmptyArray(object):

    @staticmethod
    def get_array():
        return []

class TestDataUniqueValues(object):
    data = []
    for i in range(5):
        data.append(i)
    data[::-1]  
    @staticmethod
    def get_array():
        return TestDataUniqueValues.data
    @staticmethod
    def get_expected_result():
        data = TestDataUniqueValues.get_array()
        return data.index(min(data))

class TestDataExactlyTwoDifferentMinimums(object):
    data = []
    for i in range(5):
        data.append(i)
    data[::-1]
    data.insert(0,0)

    @staticmethod
    def get_array():
        return TestDataExactlyTwoDifferentMinimums.data
    @staticmethod
    def get_expected_result():
        data = TestDataExactlyTwoDifferentMinimums.get_array()
        return data.index(min(data))


def TestWithEmptyArray():
    try:
        seq = TestDataEmptyArray.get_array()
        result = minimum_index(seq)
    except ValueError as e:
        pass
    else:
        assert False


def TestWithUniqueValues():
    seq = TestDataUniqueValues.get_array()
    assert len(seq) >= 2

    assert len(list(set(seq))) == len(seq)

    expected_result = TestDataUniqueValues.get_expected_result()
    result = minimum_index(seq)
    assert result == expected_result


def TestiWithExactyTwoDifferentMinimums():
    seq = TestDataExactlyTwoDifferentMinimums.get_array()
    assert len(seq) >= 2
    tmp = sorted(seq)
    assert tmp[0] == tmp[1] and (len(tmp) == 2 or tmp[1] < tmp[2])

    expected_result = TestDataExactlyTwoDifferentMinimums.get_expected_result()
    result = minimum_index(seq)
    assert result == expected_result

TestWithEmptyArray()
TestWithUniqueValues()
TestiWithExactyTwoDifferentMinimums()
print("OK")
```
