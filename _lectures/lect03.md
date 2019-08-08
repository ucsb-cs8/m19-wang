---
num: Lecture 3
lecture_date: 2019-08-08
desc: "Python Lists, Tuples, Namedtuples, Functions"
ready: false
pdfurl:
---

```python
# CS 8, 8-8-19

"""
There are ways to interact with a computer program
    - Using user-input
    - typing stuff into the python shell
    - reading files
    - clicking on buttons
    - mouse movement
    - ...

# Example
print("Hi, please enter your name: ")
userName = input()
print(type(userName))
print("Hello", userName)

# Example (tip calculator)
TAX_RATE = 0.1
print("Hi, please enter your name: ")
userName = input()
print("Hi", userName, ". What's the amount of your bill (not including \
tax and tip)?")
# Be careful, if input is not a float, program will crash
totalBill = float(input())
print("What is the tip percentage you would like to leave?")
tipPercentage = float(input())
taxAmount = totalBill * TAX_RATE
tipAmount = totalBill * (tipPercentage / 100)
print("The total amount to pay is $", totalBill + taxAmount + tipAmount)

# Some more terminology

- Syntax: Grammar, or how you say it
- Semantics: Meaning, or what it does

Example:
Syntactically incorrect (in python): PI equals 3.14159
Semantically incorrect (in python): PI = "apple"
"""

""" Lists
- A list is a collection of multiple values (similar to how a str is
a collection of characters)
- Note: In python, lists can be of heterogenous (different) types
- Lists can have duplicate values

evenNumbers = [2,"4",6,"8"]
print(evenNumbers)
print(type(evenNumbers))
print(evenNumbers[2])
print(evenNumbers[-1])
print(type(evenNumbers[-1]))
evenNumbers.append(10)
print(evenNumbers)
evenNumbers[2] = 60
print(evenNumbers)

#print(evenNumbers[1] + evenNumbers[2]) # Error, incompatible types
print(int(evenNumbers[1]) + evenNumbers[2]) # OK

names = ["Rick", "Morty", "Summer"]
print(names)
names.sort() # Sorts the list in lexicographical order
print(names)

names.pop() # removes last element of list
print(names)
names.pop(0) # removes element at index 0 in the list
print(names)

# Tuples
- A tuple is similar to a list, but with a small (but important)
difference
- For example, certain built-in functionality (list.sort()) works for
lists, but not tuples
- Inherently, tuples and lists are different, but logically, they're
the same
- We can change an element in a list, but we cannot change an element
in a tuple.

oddNumbers = (1,3,5,7)
print(oddNumbers)
print(type(oddNumbers))

print(oddNumbers[1])
#oddNumbers.sort() # ERROR tuples doesn't have .sort()
print(oddNumbers)
oddNumbers[1] = 30

Namedtuples
- A way to package heterogenous things into a multi-attribute item
- We can represent more complex data into a single type
- We can access attributes by the name (vs. an index like we've seen
in lists / tuples)

# Using namedtuples
# Step 1: Allow your program to use namedtuples

from collections import namedtuple

# Step 2: Design what your object looks like
Student = namedtuple("Student", "name PERM major GPA")
# parameters of function: 1st is name of the namedtuple type - Student
# 2nd is a string containing the name of the attributes

# Step 3: Create distinct student objects
s1 = Student("John Doe", 12345678, "CS", 3.5)
s2 = Student("Jane Doe", 87654321, "MUSIC", 3.9)

# Step 4: Refer to specific fields within these namedtuples with '.'
print("Name of s1:", s1.name)
print("PERM of s1:", s1.PERM)
print("Major of s1:", s1.major)
print("GPA of s1:", s1.GPA)

Defining Functions

Let's write a simple function definition, something that takes an
integer value and doubles it...

# Function definition
def double(n):
    ''' Returns 2 times the parameter ''' # Good to comment functions!
    return 2 * n

# The def double is defining the name of the function
# The (n) denotes the parameter(s) that this function will accept
# In this case, it takes a single value and is used in the function
# The name and parameter(s) of a function is referred to as a function
# signature
# The actual code (return 2 * n) is called the body of the function
# The body needs to be indented so python can associate the body's
# instructions as part of the function definition
# if the function returns a value, then a return statement is needed.

# Example
print(double(10))
print(double(double(2)))
"""
```

