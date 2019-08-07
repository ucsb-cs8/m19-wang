---
num: Lecture 2
lecture_date: 2019-08-07
desc: "Python Data Types"
ready: false
pdfurl:
---

```python
# CS 8, 8-7-19

''' Some Python data types
int: Integers representing non-decimal values
float: Floating point number representing a decimal (fractional) value
string: Represents a collection of characters
    - Ex: 'A', 'a', '1', ' ', '-', 'abc'
bool - Evaluates to either True or False
    - Ex: 4 <= 6 # Evaluate to True
    - Ex: 1 == 2 # Evaluate to False
Note: 3 and 3.0 are considered different types!
    - 3 is an integer (non-decimal value)
    - 3.0 is a float
    - Python knows what type these numbers are based on its value.
'''

""" Examples

x = 1
print(x)
print(type(x)) # int

y = 1.0
print(y)
print(type(y)) # float

x = 4 / 2
print(x)
print(type(x)) # float - division inherently returns float values
x = 4 * 2.0
print(x)
print(type(x)) # float - if one operand is a float, a float is returned
x = 4 * 2
print(x)
print(type(x)) # int - no operand is a float, just ints so value is int
# What about addition: 2 + 2.0 vs. 2 + 2 ... what types are these?
'''

x = "CS 8" # string type since it's wrapped in quotes
print(x)
print(type(x))

x = "8.0"
print(x)
print(type(x)) # str

'''
y = x + 5 # error, cannot concatenate an int to a string
print(y)
print(type(y))
'''

y = float(x) + 5
print(y)
print(type(y)) # float

'''
z = "8.0 + 5.0"
z = float(z) # error, "8.0 + 5.0" is not a valid float value
'''

# Be careful...
x = "8.0"
# x = int(x) # crash int(str) expects no decimal point!
x = int(float(x)) # OK, x is now an int type
print(x)
print(type(x))


# Boolean Examples
x = "8.0"
y = "8.0"
z = "8.00"

print(x == y) # True
print(x == z) # False
print(float(x) == float(z)) # True
print(2 * 3 > 5)
print(type(2 * 3 > 5))

''' Indexing strings and substrings
- In a string, we can extract certain pieces from it
- This is also known as "parsing" a string
- Positions in a string start at index 0
'''

schoolName = "UCSB"
print(len(schoolName)) # 4
print(type(schoolName)) # str
print(type(len(schoolName))) # int

print(schoolName[0])
print(schoolName[3])
# print(schoolName[4]) error - out of range
print(schoolName[-1]) # B (the last character, -2 index is 2nd to last..)
# print(schoolName[-5]) Error - out of range

# Extracting a substring
print(schoolName[1:3]) # CS (from position 1 up to (but not including)
                       # pos 3)

# compute salary example
hours = 40
rate = 12
salary = hours * rate
print("Salary is $",salary,"!") # sep="" for not having spaces between parts

# Escape characters - double quotes
print("hi") # prints hi without double quotes
print("\"hi\"") # prints hi with double quotes
"""
```