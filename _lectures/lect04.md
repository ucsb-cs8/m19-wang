---
num: Lecture 4
lecture_date: 2019-08-13
desc: "Immutable vs. Mutable, Python Testing"
ready: false
pdfurl:
---

```python

# 8-13-19

# Function definition
def double(n):
    ''' Returns 2 times the parameter '''
    return 2 ** n

"""
print(double("5"))
print(double(2.5))
print(double([2,3]))

# Note: A function doesn't have to return anything.
# If a function doesn't have a specific return value, it
# returns a special 'None' type.

#print(double(5))
#print(double(double(4)))
#value = double(5) + double(6)
#print(value)
#print(type(value))

Mutable vs. Immutable
* Lists in Python are MUTABLE (can change the existing list)
* Tuples in Python are IMMUTABLE (cannot change the existing tuple)

# Example
def add_to_end(s, i):
    ''' Return a string with i appended to s '''
    s = s + i
    return s

name = "Richert"
print(add_to_end(name, "!"))
print(name)

def add_to_list(L, i):
    ''' Returns a list with value i appended to list L'''
    L.append(i)
    return L

print("---")
someList = [2,4,6,8]
print(someList)
print(add_to_list(someList, 10))
print(someList)

# Why should we care about immutable vs mutable properties
# - Depending on whether or not something is mutable or immutable, it affects
# how the data is treated when passing it in a function (see Chapter 3.5)

# When immutable types are passed into a function, a COPY of that variable is
# made and used within the function.
# Once the function returns, the immutable variable does not change

# When mutable types are passed into a function, that variable is used within
# the function (no copy is made)
# Once the function returns, the mutable variable does change

from collections import namedtuple

Book = namedtuple('Book', 'title author')
b1 = Book("Harry Potter and the Goblet of Fire", "Rowling")
print(b1)
#b1.author = "J. K. Rowling" # ERROR

# seems intuitive to do this, but it's illegal
# Namedtuples are immutable and we cannot change the existing values of namedtuples
# directly

# So how do we change the author in this Book namedtuple?

# 1. Create a new object:
#b1 = Book("Harry Potter and the Goblet of Fire", "J. K. Rowling")
b1 = Book(b1.title, "J.K. Rowling")
print(b1)

# 2 Use the _replace method
b1 = b1._replace(author="J.K.R.")
print(b1)

Python Testing

- Software testing is essential to ensure behavior works as expected
- We can write "assert statements" throughout the code in order to help us test
and make sure our function behaves as expected"

assert double(2) == 4
assert double(0) == 0
assert double(-3) == -6
assert double(1234) == 2468

print("all done with tests")

# Example using pytest functions
# pytest runs functions that start with test_

def test_double_5():
    assert double(5) == 10

def test_double_negative():
    assert double(-1) == -2

def test_double_3():
    assert double(3) == 6
"""

# Recall - Booleans
# - Boolean values evaluate to True or False
# - BOOLEAN EXPRESSIONS are statements that evaluate to True or False

print(4 < 6)
print(4 < 6 and 3 < 6) #True and True --> True
print(4 == 4)
print(4 != 4)
print(4 >= 5)
print("Rich" in "Richert") # True
print("hciR" in "Richert") # False
```